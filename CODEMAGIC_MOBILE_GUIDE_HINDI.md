# मोबाइल से Codemagic पर APK कैसे बनाएं

## पहले क्या चाहिए
- GitHub account
- Codemagic account
- यही पूरा ZIP project

## चरण 1: ZIP extract करें
मोबाइल में ZIP extract करने के लिए Files, ZArchiver या कोई ZIP app इस्तेमाल करें।

Extract होने के बाद root folder में ये files दिखनी चाहिए:

- `app`
- `build.gradle.kts`
- `settings.gradle.kts`
- `gradle.properties`
- `codemagic.yaml`

ध्यान दें: `codemagic.yaml` किसी अंदर वाले extra folder में नहीं, project की root में होनी चाहिए।

## चरण 2: GitHub repository बनाएं
1. GitHub website/app खोलें।
2. New repository चुनें।
3. नाम रखें: `news-india-time-android`
4. Repository बनाएं।
5. Project की सभी files upload करें।

एक बार में folder upload न होने पर Chrome में GitHub को Desktop Site में खोलें, या GitHub-compatible mobile Git client इस्तेमाल करें।

## चरण 3: Codemagic से GitHub जोड़ें
1. Codemagic में GitHub से sign in करें।
2. `Add application` दबाएं।
3. GitHub चुनें।
4. `news-india-time-android` repository चुनें।
5. Project type में `Other / Android` चुनें।
6. Codemagic configuration में `codemagic.yaml` चुनें।

## चरण 4: APK Build करें
1. Workflow में `News India Time APK` चुनें।
2. `Start new build` दबाएं।
3. Branch में `main` चुनें।
4. Build शुरू करें।

पहली build में Gradle और dependencies download होने के कारण समय लग सकता है।

## चरण 5: APK Download करें
Build successful होने पर:
1. Build खोलें।
2. `Artifacts` section खोलें।
3. `app-debug.apk` download करें।
4. Android mobile में install करें।

Install करते समय जरूरत पड़े तो:
Settings → Install unknown apps → Browser/Files को Allow करें।

## APK का प्रकार
यह debug APK होगा। अपने mobile में testing/install के लिए सही है।
Google Play Store पर डालने के लिए signed release AAB और keystore अलग से चाहिए।

## Build fail हो तो
Codemagic की लाल error वाली अंतिम 20–30 lines का screenshot भेजें।
