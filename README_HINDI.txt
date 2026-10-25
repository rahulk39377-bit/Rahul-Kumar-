MERI SAMASYA PWA — GitHub Pages और Play Store के लिए
====================================================

इस पैकेज में:
- index.html: संशोधित Meri Samasya HTML ऐप, PWA manifest/service worker registration के साथ
- manifest.json: इंस्टॉल नाम, आइकन, start URL और display mode
- sw.js: ऐप shell cache और basic offline fallback
- icons/: 192px, 512px और maskable app icons

A. GitHub Pages पर प्रकाशित करें (मोबाइल से भी संभव, कंप्यूटर आसान)
-------------------------------------------------------------------
1. https://github.com खोलें और नया Public repository बनाएँ, उदाहरण: meri-samasya-pwa
2. ZIP को अपने डिवाइस पर Extract करें। रिपॉज़िटरी के root में ये आइटम अपलोड करें:
   index.html, manifest.json, sw.js, icons/ फ़ोल्डर
   (README_HINDI.txt भी रख सकते हैं। ZIP को सीधे रिपॉज़िटरी में डालने से वेबसाइट नहीं चलेगी।)
3. GitHub repository → Settings → Pages खोलें।
4. Build and deployment में “Deploy from a branch” चुनें। Branch: main; Folder: /(root) चुनें और Save करें।
5. GitHub द्वारा दिया गया HTTPS Pages URL खुलने तक प्रतीक्षा करें। URL का रूप आम तौर पर:
   https://YOUR-USERNAME.github.io/REPOSITORY-NAME/
6. उस URL को Chrome Android में खोलें। Menu (⋮) → “Install app” या “Add to Home screen” चुनें।
7. पहली बार ऑनलाइन खोलें ताकि ऐप के संसाधन cache हो सकें। बाद में कुछ ऐप shell ऑफलाइन खुल सकेगा।

B. Google Play Store के लिए AAB
-------------------------------
1. पहले PWA को GitHub Pages पर HTTPS URL पर प्रकाशित करें और वास्तविक Android फोन पर जाँचें।
2. https://www.pwabuilder.com/ खोलें और अपना live PWA URL दें।
3. Package for stores / Android package विकल्प चुनकर TWA पैकेज जनरेट करें।
4. जनरेट हुए पैकेज में AAB शामिल हो सकता है; उसे डाउनलोड करके Play Console के Internal testing track में अपलोड करें।
5. डिजिटल asset links (/.well-known/assetlinks.json) और signing/keystore निर्देश PWABuilder द्वारा दिए अनुसार पूरा करें। Keystore को सुरक्षित रखें और किसी से साझा न करें।
6. Play Console में privacy policy, Data safety, app content, screenshots, app icon और बाकी जरूरी listing भरें। फिर testing और review पूरा करें।

सीमाएँ / महत्वपूर्ण सूचना
------------------------
- मौजूदा ऐप localStorage इस्तेमाल करता है: रिपोर्टें उसी browser/device में रहती हैं।
- यह ऐप अपने-आप पुलिस, नगर निगम या किसी सरकारी विभाग को शिकायत नहीं भेजता।
- GitHub Pages static hosting है; इसमें रिपोर्टों के लिए database, login या admin dashboard नहीं है।
- Service worker offline shell उपलब्ध कराने का प्रयास करता है, लेकिन पहली बार online visit जरूरी है। नए अपडेट के बाद पुराने cache को बदलने के लिए sw.js में CACHE_NAME version बढ़ाएँ।
- GitHub Pages URL पर PWA इंस्टॉल हो सकता है; Google Play पर प्रकाशन अलग प्रक्रिया है और मंजूरी सुनिश्चित नहीं है।
- Play Store पर प्रकाशित करने से पहले ऐप को टेस्ट करें और वर्तमान Play Console की सभी policy/target API आवश्यकताएँ जाँचें।
