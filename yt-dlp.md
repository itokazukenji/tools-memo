```
# 動画ファイルと音声ファイルの確認
$ yt-dlp -F "https://www.youtube.com/watch?v=hoge"

# 動画ファイルと音声ファイルの選択とフォーマットの選択
$ yt-dlp -f 616+251 --merge-output-format mp4 "https://www.youtube.com/watch?v=hoge"

# ベストな音質と画質を選択してくれる
yt-dlp -f "bv*+ba/best" "https://hoge.com?v=hoge"
```
