# News India Time Android App

यह Android Studio project है।

## अभी काम करने वाले फीचर
- Gallery से केवल video चुनना
- केवल audio/music file चुनना
- Video preview
- Video export progress
- Background music को video के साथ composition में जोड़ना
- H.264 MP4 + AAC export
- Exported video को Gallery के `Movies/News India Time` folder में save करना
- Export के बाद WhatsApp/Instagram आदि पर share करना
- News India Time logo और news portal theme

## Android Studio में APK कैसे बनाएं
1. Android Studio खोलें।
2. **Open** दबाकर `NewsIndiaTimeAndroid` folder चुनें।
3. Gradle Sync पूरा होने दें।
4. Mobile में Developer Options और USB Debugging ON करें।
5. Run दबाएं, या:
   **Build → Build APK(s)**
6. APK यहाँ मिलेगा:
   `app/build/outputs/apk/debug/app-debug.apk`

## जरूरी जानकारी
- इस project को Android Studio/Gradle में compile करना जरूरी है; ZIP स्वयं APK नहीं है।
- पहली Gradle sync के लिए internet चाहिए।
- Media3 Transformer device पर video render करता है।
- बहुत लंबे/4K video में export समय और storage अधिक लगेगा।
- वर्तमान version music mixing और Gallery export पर केंद्रित है।
- Headline/caption fields UI में हैं; text/logo को final video pixels पर burn करने वाला overlay renderer अगला module है।
- AI auto-caption के लिए speech-to-text API/model जोड़ना होगा।

## तकनीक
- Kotlin
- Android Views + ViewBinding
- Jetpack Media3 Transformer 1.10.1
- ExoPlayer preview
- Android MediaStore Gallery save