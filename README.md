# TNX EDITZ app (Android)

Is app me 3 screen hain:
- **Home**: "Place an order" aur "Admin" ke 2 bade button.
- **Place an order** (`www/form.html`): customer service chunta hai (Banner, Video edit, Thumbnail, Logo, Reel / Short, Poster, Other), details bharta hai, Send order dabata hai. Message copy hota hai aur Instagram chat (ayush_maurya__321_) khulti hai.
- **Admin** (`www/desk.html`): admin code **TNX2026** se khulta hai. Order Desk me orders add, edit, delete, status badlo.

## APK kaise banaye (computer pe kuch install nahi karna)
1. github.com pe free account banao, **New repository** banao (Private rakho).
2. Is poore folder ki files us repository me upload karo (Add file -> Upload files).
3. Repository me **Actions** tab kholo -> **Build Android app** -> **Run workflow**.
4. 5-10 minute baad run complete hone pe neeche **Artifacts** me milega:
   - `TNX-EDITZ-APK`: ye APK phone me seedha install hota hai (WhatsApp se bhej ke bhi).
   - `TNX-EDITZ-PlayStore-AAB`: ye Play Store pe upload karne ki file hai.

## Play Store pe daalne ke liye
1. play.google.com/console pe developer account banao (one-time US$25 fee).
2. Ek upload key banao (apne computer pe, ek baar):
   `keytool -genkeypair -v -keystore upload.jks -alias upload -keyalg RSA -keysize 2048 -validity 10000`
   Is file aur password ko surakshit rakho. Kho gayi to update nahi daal paoge.
3. GitHub repository -> Settings -> Secrets and variables -> Actions me ye 3 secrets daalo:
   - `KEYSTORE_BASE64`: `base64 -w0 upload.jks` ka output
   - `KEYSTORE_PASSWORD`: keystore ka password
   - `KEY_ALIAS`: `upload`
4. Workflow dobara chalao. Ab `TNX-EDITZ-PlayStore-AAB` signed hoga. Use Play Console me app banake upload karo.

## Dhyan rakhne wali baatein
- Admin ke orders usi phone me save hote hain jisme app chal raha hai. Do phones me alag-alag list dikhegi.
- Customers ke orders Instagram DM me aate hain. Order Desk me inhe "+ New order" -> "Fill from the customer's message" se daalo.
- Admin code app ke andar hai, isliye ye halka sa lock hai, pakka security nahi.
- Instagram ka naam badalna ho to `www/form.html` me `IG_HANDLE` badlo.
