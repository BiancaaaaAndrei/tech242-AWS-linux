# Creating Access Keys and Configuring AWS CLI

## Creating Access Keys:

1. **Navigate to Security Credentials:**
   - Click on your username (e.g., Bianca) in the AWS Management Console.
   - Go to "Security Credentials."

2. **Access Access Key Settings:**
   - Scroll down and locate the option to "Create Access Key."

3. **Selecting Usage Type:**
   - Choose the appropriate usage type based on your needs (e.g., CLI).
   - AWS provides alternative recommendations based on your selection.

4. **Understanding Recommendations:**
   - Pay attention to AWS recommendations for CLI usage (e.g., CloudShell, CLI V2).
   - Acknowledge the recommendation and proceed.

5. **Acknowledging Recommendation:**
   - Click on "I understand the above recommendation" to proceed.

6. **Creating Access Key:**
   - Confirm your intent to create an access key.
   - Retrieve the access key and secret access key at this stage.

7. **Configuring AWS CLI:**
   - Use the access key and secret access key for CLI and SDK integration.
   - Note: This is the only time you'll be able to access the secret access key.

## Configuring AWS CLI:

1. **Initiate CLI Configuration:**
   - Open your terminal or command prompt.

2. **Run Configuration Command:**
   - Enter the command: `aws configure` to configure the AWS CLI.

3. **Enter Access Key ID:**
   - Provide the access key ID obtained earlier and press Enter.

4. **Enter Secret Access Key:**
   - Enter the secret access key obtained earlier and press Enter.

5. **Enter Default Region Name:**
   - Specify the default region name (e.g., eu-west-1) based on your preference.

6. **Enter Default Output Format:**
   - Press Enter to keep the default output format.

7. **Verification:**
   - Confirm the successful configuration of the AWS CLI.

8. **Testing AWS CLI:**
   - Use the CLI command (e.g., `aws iam list-users`) to verify functionality.
   - Observe similar information as in the Management Console.
![IAM list-users](<../../../readme-images/iam/iam users.png>)

1. **Adjusting Permissions:**
   - Experiment by removing permissions from a user (e.g., Bianca) in the IAM console.
   - Observe the impact on both the Management Console and the CLI.

2.  **Final Note:**
    - Remember to add the user back to the appropriate group to regain permissions.

