# GitHub के माध्यम से वेरसेल पर डिप्लॉय करने के निर्देश

## 1. GitHub अकाउंट बनाएं (अगर पहले से नहीं है)
1. [GitHub.com](https://github.com) पर जाएं
2. "Sign Up" बटन पर क्लिक करें
3. अपना ईमेल, पासवर्ड आदि दर्ज करके अकाउंट बनाएं

## 2. एक नया रिपॉजिटरी बनाएं
1. अपने GitHub डैशबोर्ड पर "New" बटन पर क्लिक करें
2. रिपॉजिटरी नाम दें (जैसे "ppr-shashwat")
3. "Public" या "Private" विकल्प चुनें
4. "Create repository" पर क्लिक करें

## 3. अपने प्रोजेक्ट को GitHub पर पुश करें

### 3.1 Git इंस्टॉल करें (अगर नहीं है)
- Windows पर: [git-scm.com](https://git-scm.com/download/win) से डाउनलोड करें
- Mac पर: Terminal में `brew install git` चलाएं
- Linux पर: `sudo apt-get install git` या अपने डिस्ट्रिब्यूशन के अनुसार कमांड चलाएं

### 3.2 Git को सेटअप करें
टर्मिनल या कमांड प्रॉम्प्ट खोलें और निम्न कमांड चलाएं:
```bash
git config --global user.name "आपका नाम"
git config --global user.email "आपका-ईमेल@example.com"
```

### 3.3 अपने प्रोजेक्ट में Git इनिशियलाइज़ करें
अपने प्रोजेक्ट फोल्डर में जाएं और निम्न कमांड चलाएं:
```bash
# node_modules फोल्डर को हटाएं (गिटहब पर अपलोड न करने के लिए)
rm -rf node_modules
# या node_modules फोल्डर को मैन्युअली डिलीट करें

# आपके प्रोजेक्ट में Git इनिशियलाइज़ करें
git init

# सभी फाइल्स को स्टेज करें
git add .

# कमिट करें
git commit -m "Initial commit"

# GitHub रिपॉजिटरी को रिमोट के रूप में जोड़ें
git remote add origin https://github.com/आपका-यूजरनेम/आपका-रिपॉजिटरी-नाम.git

# पुश करें
git push -u origin main
```
नोट: अगर main ब्रांच नहीं बनी है, तो `git push -u origin master` का प्रयोग करें।

## 4. वेरसेल अकाउंट बनाएं और GitHub से कनेक्ट करें

### 4.1 वेरसेल अकाउंट बनाएं
1. [vercel.com](https://vercel.com) पर जाएं
2. "Sign Up" पर क्लिक करें
3. "Continue with GitHub" चुनें और अपने GitHub अकाउंट से लॉगिन करें

### 4.2 GitHub रिपॉजिटरी को इंपोर्ट करें
1. वेरसेल डैशबोर्ड में "Add New..." बटन पर क्लिक करें
2. "Project" विकल्प चुनें
3. "Import Git Repository" सेक्शन में अपने GitHub रिपॉजिटरी को ढूंढें और "Import" पर क्लिक करें

### 4.3 प्रोजेक्ट कॉन्फिगरेशन
1. प्रोजेक्ट नाम को वैसे ही रखें या बदलें
2. "Framework Preset" के लिए "Next.js" चुनें
3. अन्य डिफॉल्ट सेटिंग्स को वैसे ही रखें
4. "Deploy" बटन पर क्लिक करें

## 5. डिप्लॉयमेंट देखें
वेरसेल आपके एप्लिकेशन को बिल्ड और डिप्लॉय करेगा। बिल्ड प्रोसेस पूरा होने के बाद, आपको एक लिंक मिलेगा (उदाहरण: https://ppr-shashwat.vercel.app)।

## 6. अपडेट्स पुश करें
जब भी आप अपने प्रोजेक्ट में परिवर्तन करते हैं:
```bash
# पहले node_modules इंस्टॉल करें अगर आपने हटा दिया था
npm install

# परिवर्तन करें और टेस्ट करें
npm run dev

# परिवर्तन कमिट करें
git add .
git commit -m "अपडेट का विवरण"
git push
```

वेरसेल आपके GitHub रिपॉजिटरी में किए गए हर push के बाद ऑटोमैटिक रूप से आपके एप्लिकेशन को फिर से डिप्लॉय कर देगा।

## अतिरिक्त टिप्स
- अपना कस्टम डोमेन जोड़ने के लिए वेरसेल डैशबोर्ड में अपने प्रोजेक्ट के "Domains" सेक्शन में जाएं
- एनवायरनमेंट वेरिएबल्स सेटअप करने के लिए वेरसेल डैशबोर्ड में "Settings" → "Environment Variables" में जाएं 