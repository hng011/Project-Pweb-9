# DDHZ Todos 📒

A Simple React JS and Laravel web application for todolist app with a simple OTP implementation for account activation using gmail

## Contributors 🤸
1. [@hng011](https://github.com/hng011)
2. [@danaradhytia](https://github.com/danaradhytia) 
3. [@skuuzie](https://github.com/skuuzie) 
4. [@damon](https://github.com/Awaviviana09)

## Getting Started ⚒️
Installing composer.json and package.json
```bash
composer install

npm install
```

Create `.env` file from copying `.env.example.com`
```bash
cp .env.example .env
```

Update `.env` file
1. Configure your own database here

![image](https://github.com/hng011/Project-Pweb-9/assets/93465725/40f3f369-5afe-4d8d-9016-3f43c50a697a)

3. Configure your Gmail SMTP server

![image](https://github.com/hng011/Project-Pweb-9/assets/93465725/6f0b341d-87b5-4b56-9ba2-275332463720)


Generating an app key
```bash
php artisan key:generate
```

Migrating database
```bash
php artisan migrate
```

Run Laravel server and React JS server
```bash
npm run dev

php artisan serve
```

Run the Laravel server by clicking the link

![image](https://github.com/hng011/Project-Pweb-9/assets/93465725/dc5e7ef2-9c1e-4c53-8db8-0dfa3393ea90)
