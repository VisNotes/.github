## Migrations CLI

```bash
dotnet ef database update -s .\Ocr.Api\ -p .\Ocr.Data\ --context OcrDbContext
```

## Local Dev Env Vars Needed

1. DI_KEY
    - Azure Cognitive Services Key
2. DI_ENDPOINT
    - Azure Cognitive Services Endpoint
3. ASPNETCORE_ENVIRONMENT
    - Development
4. OCR_STORAGE_PATH *?*
    - Example: C:\Users\justin\code\OCR\ocr_storage