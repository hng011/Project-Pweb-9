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


## Laravel + React JS setup ⚙️

1. <pre>composer create-project laravel/laravel your-folder-name</pre>

2. Run this command on your terminal `cp .env.example .env` and configure your database. It's actually make a copy of `.env.example` and paste it with name `.env`
<br />

3. <pre>php artisan key:generate</pre>

4. <pre>composer require inertiajs/inertia-laravel</pre>

5. <pre>npm install @inertiajs/react @vitejs/plugin-react react react-dom @inertiajs/inertia-react</pre>

6. <pre>php artisan inertia:middleware</pre> 

7. Go to kernel.php and put this as the last item in `web` middleware group
<pre>
\App\Http\Middleware\HandleInertiaRequests::class,
</pre>

<br />

8. add `app.blade.php` in views (default for react in inertia) and put this code within the `app.blade.php` file
<pre>
coming soon!!!
</pre>


9. update vite.config.js
<pre>
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import react from '@vitejs/plugin-react';

export default defineConfig({
    plugins: [
        react(),
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
    ],
});
</pre>

10. Put these into app.js within resources/views
**Set all of your react file into .jsx** ❗❗❗
<pre>
import './bootstrap'

import React from 'react'
import {createRoot} from 'react-dom/client' //here
import {createInertiaApp } from '@inertiajs/inertia-react'
import {resolvePageComponent} from 'laravel-vite-plugin/inertia-helpers'

createInertiaApp({
    resolve: (name) => resolvePageComponent(`./Pages/${name}.jsx`,import.meta.glob('./Pages/**/*.jsx')),
    setup({ el, App, props }) {
        createRoot(el).render(<App {...props} />) //and here
    },
})
</pre>

**Actually you can delete the `import './bootstrap'` end delete the `bootsrap.js` file**

11. Create `Pages` folder within `resources/js/`. It will be the main page for your react app.

12. Inside the `Pages` you have created, add new file and name it with `Test` and put the code below. This is for test your react app.
<pre>
import React from 'react';

export default function Test(){
    return 'test';
    }
</pre>

13. go to `web.php` within routes folder and then put this into as an import statement `use Inertia\Inertia;`
<br />

14. Add a new route in `web.php`
<pre>
Route::get("/test", function () {
    return Inertia::render('Test');
});
</pre>

15. run `npm run dev` and `php artisan serve`
<br />

16. Type `/test` to url
<br />

17. You're fully configured!
