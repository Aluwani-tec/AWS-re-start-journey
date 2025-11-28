# STATIC WEBSITE PROJECT 

## 1. Overview
- Built a simple restaurant website using HTML, CSS, and images.
- Hosted the website on Amazon S3 using Static Website Hosting.
- Site includes homepage, menu page, and a basic booking/contact section.

## 2. What I Learned
- How S3 buckets store files (objects) and how folder paths work.
- How to enable Static Website Hosting on S3.
- How to write and fix bucket policies to allow public access.
- How to upload files correctly and test the S3 endpoint.

## 3. Challenges Faced
- "Access Denied" errors due to wrong bucket policy.
- S3 Block Public Access was still on → site couldn’t load.
- Wrong file paths caused broken images.
- Forgetting to set `index.html` as the main page.
- Team files were different → needed to standardize folders.

## 4. Wins
- Website successfully hosted and publicly accessible.
- Fixed all permissions and policy issues.
- Learned how S3 endpoints work.
- Understood how to store images, HTML, and CSS in one bucket.
- Improved troubleshooting skills through real errors.

## 5. Skills Gained
- S3 Static Website Hosting
- Bucket Policies & Permissions
- HTML/CSS structuring
- Debugging file paths and access issues
- GitHub documentation and version control

## 6. Summary
This project helped me understand S3 much better. I learned how to host a real website, fix permission problems, and organise project files properly. It gave me confidence and a practical AWS project I can show to employers.

## 4. Security Basics
- Buckets are private by default  
- Public access only when needed  
- Bucket Policies control who can read files  

