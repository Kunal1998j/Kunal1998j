<!DOCTYPE html>
<html>
<head>
    <title>Redirecting...</title>
    <script>
        function rotateLink() {
            // Your base link
            const baseLink = "https://city1.maksoftbox.com/MarketingEnquiry/EnquiryQRCode?Id=df80e48d-f9f5-48a2-8341-e652ac165f28&SecurityStamp=30099c34-a393-438c-bf6d-71d3fc048c45";
            
            // Get current time in minutes to create a unique rotation ID
            const now = new Date();
            const rotationId = now.getFullYear() + "" + now.getMonth() + "" + now.getDate() + "" + now.getHours() + "" + now.getMinutes();

            // Append the rotation ID to the link so it "refreshes" every minute
            const finalLink = baseLink + "&rot=" + rotationId;

            // Redirect the user
            window.location.href = finalLink;
        }

        // Run on page load
        window.onload = rotateLink;
    </script>
</head>
<body>
    <p>Redirecting you to the latest secure link...</p>
</body>
</html>
