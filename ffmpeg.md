```
# 動画と字幕の結合
ffmpeg -i input.mp4 -vf "subtitles=subtitles.srt:force_style='FontName=YuGothic,FontSize=18,MarginV=14'" -c:v libx264 -crf 16 -preset slow -c:a copy output.mp4
```
