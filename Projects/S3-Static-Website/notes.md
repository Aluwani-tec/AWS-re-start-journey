# S3 Static Website Project - AWS re/Start (Group Work)

This project was completed as part of group work during the AWS re/Start Programme. Our objective was to deploy a functional static website using Amazon S3 and understand how S3 hosting, permissions, and bucket policies work in a real environment.

---

## 1. Project Goal
Deploy a static website (HTML, CSS, images) on Amazon S3 and make it publicly accessible through the S3 website endpoint.

---

## 2. Bucket Setup

![Bucket Setup](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/S3-Static-Website/images/s3-static-site-setup.png?raw=true)

We created a bucket named **the-taste-of-africa-static-website**, disabled Block Public Access, and prepared it for static hosting.

Key actions:
- Created the S3 bucket  
- Disabled “Block Public Access”  
- Enabled Static Website Hosting  
- Uploaded website files  

---

## 3. Uploading Website Files

![Objects](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/S3-Static-Website/images/s3-static-website-objects.png?raw=true)

File structure inside the bucket:
index.html
Stylesheet.css
Images/


This ensured the site loads correctly without broken paths.

---

## 4. Permissions and Public Access

### Bucket Policy

![Bucket Policy](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/S3-Static-Website/images/s3%20web.PNG?raw=true)

We applied a bucket policy that allows public read access to all objects.  
This was required because the website must be accessible to users without authentication.

### Object Permissions (ACL)

![Object Permissions](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/S3-Static-Website/images/s3%20website.PNG?raw=true)

We confirmed that the `index.html` object was readable to the public through ACL and the bucket policy.

---

## 5. Website Preview

### Home Page

![Home Page](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/S3-Static-Website/images/s3%20websit.PNG?raw=true)

The main landing page loaded successfully using the S3 hosting endpoint.

---

## 6. Group Challenges

We encountered several common S3 hosting issues and resolved them together:

### Public Access Blocked
- The site refused to load at first.
- Fix: Disabled Block Public Access and reapplied a valid bucket policy.

### CSS and Images Not Loading
- HTML loaded, but styling didn’t.
- Root Cause: Some objects didn’t inherit permissions.
- Fix: Ensured wildcard `/*` was added in the bucket policy to include all files.

### Confusion Between ACL vs Bucket Policy
- Some team members trusted ACLs even when bucket policy still blocked access.
- Lesson: The bucket policy is the main control. ACL alone is not enough.

### Missing or Misplaced Files
- A few images were accidentally uploaded outside the Images folder.
- Fix: Re-uploaded and corrected the folder structure.

---

## 7. Wins

As a team, we achieved:

- Full deployment of a static website in S3  
- A working website endpoint  
- Correct bucket and object permissions  
- Improved understanding of how static hosting replaces a traditional web server  
- Better confidence troubleshooting S3 errors  

---

## 8. Lessons Learned

- S3 requires both **public access settings AND a correct bucket policy**.
- S3 is not a web server - it only serves static files.
- Permissions issues are the most common cause of broken CSS and images.
- The S3 website endpoint is different from the S3 object URL.
- Group collaboration helped in identifying mistakes faster.

---

## 9. Summary

This project strengthened our overall understanding of:
- Static website hosting  
- Bucket policy design  
- Object permissions  
- Error troubleshooting  
- Realistic cloud deployment practices  

It serves as a practical demonstration of hands-on cloud skills gained during AWS re/Start.

