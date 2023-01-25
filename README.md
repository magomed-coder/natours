# natours 

## Запуск программы
### 1. Скачайте файлы на компьютер

### 2. Установите зависимости
Пройдите в папку natours и пропишите 
```bash
npm install
```
отдельно установите nodemon
```bash
npm install -g nodemon
```

### 3. В папке natours в файле config.env запишите значение для следующих переменных окружения 
```javascript 
DATABASE=your_database_url (вместо <password> напишите <PASSWORD>)
DATABASE_PASSWORD=mongoose-password

JWT_SECRET=my-ultra_secure_and_ultra_long_secret_32chars

EMAIL_FROM=your-email

SENDGRID_USERNAME=from-sendgrid
SENDGRID_PASSWORD=your-secret-key-from-sendgrid

EMAIL_USERNAME=mailtrap_username
EMAIL_PASSWORD=mailtrap_password
EMAIL_HOST=mailtrap_host
EMAIL_PORT=mailtrap_port

STRIPE_SECRET_KEY=your-secret-key-from-sttipe
```

### 4. Загрузка данных в MongoDB
В папке models в файле userModel.js закомментируйте

```javascript 
/* userSchema.pre("save", async function (next) {
  // Only run this function if password was actually modified
  if (!this.isModified("password")) return next();

  // Hash the password with cost of 12
  this.password = await bcrypt.hash(this.password, 12);

  // Delete passwordConfirm field
  this.passwordConfirm = undefined;
  next();
});

userSchema.pre("save", function (next) {
  if (!this.isModified("password") || this.isNew) return next();

  this.passwordChangedAt = Date.now() - 1000;
  next();
}); */
```

после в теминале напишите 
```bash
npm run importData
```
раскомментируйте обратно

### 5. Запуск
В терминале напишите
```bash
npm start
```
В проект планиуется добавить 
1) карту со всеми локациями(библиотека leaflet) при проходя на страницу отдельного тура
2) двойную аутентефикацию
3) переписать фронт на реакт



