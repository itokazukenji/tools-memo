```
# 動画ファイルと音声ファイルの確認
$ yt-dlp -F <URL>

# 動画ファイルと音声ファイルの選択とフォーマットの選択
$ yt-dlp -f 616+251 --merge-output-format mp4 <URL>

# ベストな音質と画質を選択してくれる
yt-dlp -f "bv*+ba/best" <URL>

# 動画から最上級の音声ファイルを取り出す
yt-dlp -x --audio-format mp3 --output '/path/to/directory/%(title)s.%(ext)s' --audio-quality 0 <URL>

# 画質は指定、音声は最高音質
yt-dlp -f "bv[height=1080]+ba/bestvideo[height=1080]+bestaudio" -o "%(title)s.%(ext)s" <URL>
```
