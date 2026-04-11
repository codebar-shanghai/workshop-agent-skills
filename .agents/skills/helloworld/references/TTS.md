# TTS

## How to generate

1. Suppose at the stage the text and language id are known.
2. Check whether `curl` is available in the current environment. The command used for this check may differ between Windows and Unix-like systems. If `curl.exe` isn't available on the running Windows system, use `Invoke-WebRequest`, the built-in PowerShell cmdlet as fallback. If PowerShell isn't installed on the running Windows system, do not proceed.
3. Run the command that is runnable on the host system, either `curl` or `Invoke-WebRequest`, to send the text and language id as form data to the server `http://127.0.0.1:5002/tts`, and save the audio file to the root of the repo with the filename `lang_id.wav`.

## curl Example

If the previous translation returns `你好世界` as text and `zh` as the language id, then the following request is sent and the audio file should be saved as `zh.wav`.

```sh
curl -X POST http://127.0.0.1:5002/tts -F "text=你好世界" -F "language=zh" --output zh.wav
```

## Invoke-WebRequest Example

```powershell
Invoke-WebRequest -Uri http://127.0.0.1:5002/tts -Method Post -Form @{
  text = "你好世界"
  language = "zh"
} -OutFile "zh.wav"
```
