# Use a web server base image, for example, nginx
FROM nginx:alpine

# Set environment variable for the back-end URL
ENV WS_BACK_URL http://my-flask-app-backend:5000

# Copy your HTML files and any other static assets to the container
COPY . /usr/share/nginx/html

# Expose port 80 (default for HTTP)
EXPOSE 80

# Use entrypoint to set environment variable and start the server
ENTRYPOINT ["/bin/sh", "-c", "sed -i 's@BACK_URL@$WS_BACK_URL@g' /usr/share/nginx/html/index.html && exec nginx -g 'daemon off;'"]
