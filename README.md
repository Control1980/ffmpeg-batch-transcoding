# FFmpeg批量转码<a href='https://github.com/BtbN/FFmpeg-Builds/releases'>【原始文件链接】
<h1>批处理文件设置：</h1>
@echo off<br>
::在下方设置要处理的视频或音频格式，这里列出了一些主要的视频格式<br>
set Ext=*.avi,*.mp4,*.wmv,*.flv,*.mkv,*.rmvb,*.rm,*.3gp,*.ts<br>
md output<br>
echo 开始视频转换<br>
::在下方设置输出格式，这里输出为mp4，可自行更改<br>
for %%a in (%Ext%) do (echo 正在转换：%%a <br>ffmpeg -loglevel quiet -i "%%a" -f mp4 -c copy "output\%%~na.mp4" -y)<br>
echo 转换完成<br>
pause
