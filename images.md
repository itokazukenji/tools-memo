```
magick mogrify -format webp *.jpg

sips -Z 768 *.jpg

tinypng *.jpg


find . -type f \( -iname '*.jpg' -o -iname '*.jpeg' -o -iname '*.png' \) -print0 |
while IFS= read -r -d '' file; do
    width=$(sips -g pixelWidth "$file" 2>/dev/null | awk '/pixelWidth/ {print $2}')

    [ -z "$width" ] && continue

    if [ "$width" -le 2000 ]; then
        echo "SKIP: $file ($width px)"
        continue
    fi

    temp="${file}.tmp"

    case "${file##*.}" in
        jpg|JPG|jpeg|JPEG)
            sips -s format jpeg -s formatOptions 85 \
                --resampleWidth 2000 "$file" --out "$temp" >/dev/null
            ;;
        png|PNG)
            sips -s format png \
                --resampleWidth 2000 "$file" --out "$temp" >/dev/null
            ;;
    esac

    if [ -f "$temp" ]; then
        mv "$temp" "$file"
        echo "RESIZED: $file ($width → 2000px)"
    else
        echo "ERROR: $file"
    fi
done
```
