git reset --hard HEAD && git pull origin dev && composer install && composer du && php artisan optimize:clear && php artisan migrate --force
