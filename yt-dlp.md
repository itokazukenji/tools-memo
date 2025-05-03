```
# 動画ファイルと音声ファイルの確認
$ yt-dlp -F "https://www.youtube.com/watch?v=hoge"

# 動画ファイルと音声ファイルの選択とフォーマットの選択
$ yt-dlp -f 616+251 --merge-output-format mp4 "https://www.youtube.com/watch?v=hoge"

# ベストな音質と画質を選択してくれる
yt-dlp -f "bv*+ba/best" "https://hoge.com?v=hoge"

# 動画から最上級の音声ファイルを取り出す
yt-dlp -x --audio-format mp3 --output '/path/to/directory/%(title)s.%(ext)s' --audio-quality 0 'https://www.youtube.com/watch?v=taj2BwNSq18'

# 画質は指定、音声は最高音質
yt-dlp -f "bv[height=1080]+ba/bestvideo[height=1080]+bestaudio" -o "%(title)s.%(ext)s" <URL>
```
