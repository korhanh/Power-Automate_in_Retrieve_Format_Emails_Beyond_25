# Power Automate: Send an HTTP Request to Retrieve and Format Emails

This project demonstrates how to use Microsoft Power Automate to retrieve more than 25 emails from an inbox using the "Send an HTTP request" action, filter the data, and convert it into an HTML table.

## How It Works

1. Data Retrieval**: The default "Get emails" action in Power Automate typically retrieves only 25 emails. To retrieve more, use the "Send an HTTP request" action. For example, use the following endpoint to fetch 50 emails:
   ```plaintext
   https://graph.microsoft.com/v1.0/users/your_email_adress/mailFolders/Inbox/messages?$top=50&$select=sender,subject,body
   ```

2. Filtering: Use the $select query parameter to filter the data you retrieve. For instance, you can specify only the sender, subject, and body fields.

3. Variable Initialization: Use the "Initialize variable" action to convert the retrieved email data into an array format.

4. Data Looping: Utilize the "Apply to each" action to loop through the email data, processing and formatting it as needed.
  ```plaintext
   body('Send_an_HTTP_request')?['value']
   ```
5. Append to array variable
  ```plaintext
{
  "eMails Subject": @{item()?['subject']}
}
  ``` 
6. HTML Table Creation: Convert the processed email data into an HTML table using the "Create HTML table" action.

![get-eMails](https://github.com/korhanh/Power_Automate_in_Retrieve_Format_Emails_Beyond_25/blob/main/geteMails.png)


## Features

- Retrieve More Than 25 Emails: Use the "Send an HTTP request" action to fetch more than 25 emails.
- Data Filtering: Filter the data using the $select query parameter to include only specific fields (e.g., sender, subject, body).
- Dynamic Table Creation: Converts email data into an HTML table format.
- Easy Integration: Easily integrates into Power Automate flows.
  
## Requirements

- Microsoft Power Automate subscription
- Basic knowledge of creating Power Automate flows

## Getting Started

- Import the provided template into your Power Automate environment.
- Adjust the endpoint and data settings according to your needs.



## Contributions and Feedback

Contributions to this project are welcome! If you encounter any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](https://github.com/korhanh/Power_Automate_in_Retrieve_Format_Emails_Beyond_25/blob/main/LICENSE).

Feel free to use, modify, and distribute this project according to the terms specified in the license.

## Credits

This project is created and maintained by [korhanh]([link_to_your_github_profile](https://github.com/korhanh)).

If you use this project or find it helpful, consider giving it a star on GitHub!


