FROM php:7.2.5

# Install dependencies to compile PHP extensions
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

# Install necessary PHP extensions
RUN install-php-extensions gd ldap zip pdo_mysql

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set the working directory inside the container
WORKDIR /app

# Copy the current directory contents to the container
COPY . /app

# Install PHP dependencies using composer
RUN composer install


# Command to run the Laravel server
CMD php artisan serve --host=0.0.0.0 --port=8090

# Expose port 8090
EXPOSE 8090
