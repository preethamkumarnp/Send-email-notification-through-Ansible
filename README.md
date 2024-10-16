# Ansible Playbook for Server Ping and Email Notification

This Ansible playbook performs a simple ping to all specified hosts and sends an email notification upon successful execution.

## Requirements

- Ansible 2.10 or higher
- Internet access for sending emails
- SMTP server credentials (Gmail in this case)
- The `community.general` collection must be installed for the email module

## Prerequisites

1. **Ansible Installation**: Ensure you have Ansible installed on your control machine. You can install it via pip:

   ```bash
   pip install ansible
2. **Install Required Collection**: Install the community.general collection:
    ```bash
    ansible-galaxy collection install community.general
3. Gmail Configuration:
   * Enable Less Secure Apps or use an App Password if 2-Step Verification is enabled.

## Configuration
# Playbook Configuration

To set up your playbook, make sure to replace the placeholder values with your actual information as follows:

1. **Replace `your_email_address`** with your actual Gmail address.
2. **Replace `apppassword/mailpassword`** with your actual app password or Gmail password.
3. **Replace `destination_mail_address`** with the email address you want to receive the notification.

### Example Configuration

  * ```yaml
    email:
      sender: your_email_address
      password: apppassword/mailpassword
      recipient: destination_mail_address
 # Usage

1. Save the playbook in a YAML file, e.g., `ping_and_notify.yml`.

2. Run the playbook using the following command:

   ```bash
   ansible-playbook ping_and_notify.yml -i your_inventory_file
3. Replace your_inventory_file with your actual Ansible inventory file that lists the hosts you want to ping.

## Playbook Breakdown

* Ping Task
  - **Description**: Uses the `ansible.builtin.ping` module to check connectivity to the specified hosts.

* Email Notification
  - **Description**: Utilizes the `community.general.mail` module to send an email notification upon successful pinging of the hosts.
   
