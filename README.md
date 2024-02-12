# cloudfront
Documentation on how to access an S3 bucket using CloudFront, with a custom domain registered in Route 53

**Step 1: Set Up S3 Bucket:**

- Log in to the AWS Management Console.
- Navigate to the Amazon S3 service.
-Create a new S3 bucket or select an existing one.
- Upload your content (html,css file for CV) to the bucket.
- Configure bucket permissions to allow public access to objects.

![CloudFront_S3Bucket_SS](https://github.com/SanjuSunny28/cloudfront/assets/81848448/e5d4e954-ec37-4770-b41e-437b72315762)


**Step 2: Obtain SSL Certificate:**

- Go to the AWS Certificate Manager (ACM) console.
- Request a new SSL certificate for your custom domain.
- Follow the prompts to validate the certificate using DNS validation or email validation.
- Once validated, the certificate will be issued and available for use.

  ![CloudFront_ACM_SS](https://github.com/SanjuSunny28/cloudfront/assets/81848448/95a18f37-edd7-4705-9b14-41d5f2db94af)

**Step 3: Create CloudFront Distribution:**

- Navigate to the Amazon CloudFront console.
- Click on "Create Distribution".

    ![CloudFront_Distribution1_SS](https://github.com/SanjuSunny28/cloudfront/assets/81848448/aa75a6a8-2f37-4c1d-887c-a49ba9b13c64)
  
- Specify the S3 bucket as the origin for the distribution.

  ![CloudFront_Distribution2_SS](https://github.com/SanjuSunny28/cloudfront/assets/81848448/1f28077e-68a1-474b-ac2c-44b05dbeb9bf)
  
- Configure other settings such as cache behavior, logging, and SSL certificate.
- Enable HTTPS and select the SSL certificate obtained from ACM.

  ![CloudFront_Distribution3_SS](https://github.com/SanjuSunny28/cloudfront/assets/81848448/e04df80a-3acb-406c-b366-5449c81a000f)
  
- Review the settings and create the CloudFront distribution.


  





  

**Step 4: Configure Route 53:**

- Go to the Amazon Route 53 console.
- Select the hosted zone corresponding to your custom domain.
- Create a new record set with the desired name (here it is : sanjusunny.click).
- Choose "Alias" as the record type and select the CloudFront distribution domain name as the alias target.
- Save the changes and wait for the DNS propagation to complete.

![CloudFront_Route53_SS](https://github.com/SanjuSunny28/cloudfront/assets/81848448/25ce7e20-1345-4b01-9e4b-db96000a5bcd)

**Step 5: Testing:**

- Visit  custom domain sanjusunny.click in a web browser.
- Ensure that the content from your S3 bucket is served securely over HTTPS.
- Verify that the custom domain is displayed in the browser's address bar.
- Test different pages or objects to confirm that the setup is working as expected.

successfully set up Amazon CloudFront to serve content from your Amazon S3 bucket with a custom domain registered in Amazon Route 53.Content is now delivered securely and efficiently to your users, providing a seamless browsing experience.
(The current domain name get disabled , you can access the CV by clicking CloudFront distribution name :d32x5xajs5ha4c.cloudfront.net)
