# Use the official Nginx image as a base
FROM nginx:latest

# Set the working directory inside the container
WORKDIR /usr/share/nginx/html

# Remove the default Nginx static content
RUN rm -rf ./*

# Copy your static files to the Nginx working directory
COPY . .

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]