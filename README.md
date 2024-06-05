# Creating Users and Groups in Active Directory using PowerShell

## Overview

This repository contains scripts and documentation to help administrators create and manage users and groups in Active Directory (AD) using PowerShell. PowerShell provides a powerful and flexible way to automate AD tasks, making it easier to manage large numbers of users and groups.

## Prerequisites

Before using the scripts in this repository, ensure you have the following prerequisites:

1. **Active Directory Module for PowerShell**: This module is required to run the AD-specific cmdlets. It is available in the Remote Server Administration Tools (RSAT).
   - To install RSAT, use the following command on a Windows 10 machine:
     ```powershell
     Add-WindowsFeature -Name RSAT-AD-PowerShell
     ```
2. **Administrative Privileges**: You must have sufficient privileges to create and manage users and groups in AD.
3. **PowerShell 5.1 or later**: Ensure you have a compatible version of PowerShell installed on your system.

## Getting Started

1. **Clone the Repository**: Clone this repository to your local machine using the following command:
   ```sh
   git clone https://github.com/yourusername/AD-User-Group-Management.git
   ```

2. **Navigate to the Directory**: Change to the directory containing the scripts.
   ```sh
   cd AD-User-Group-Management
   ```

## Usage

### Creating Users

To create users in Active Directory, you need a CSV file containing the user details. The CSV file should have the following columns:
- `FirstName`
- `LastName`
- `Username`
- `Password`
- `OU` (Organizational Unit where the user will be created)

Place your CSV file in the `data` directory of this repository.

### Creating Groups

To create groups, you need a CSV file with the following columns:
- `GroupName`
- `Description`
- `OU` (Organizational Unit where the group will be created)

Place your CSV file in the `data` directory of this repository.

### Running the Scripts

1. **Open PowerShell**: Open a PowerShell prompt with administrative privileges.

2. **Import the CSV and Execute Scripts**:
   - For creating users, run:
     ```powershell
     .\Create-ADUsers.ps1 -CSVPath .\data\users.csv
     ```
   - For creating groups, run:
     ```powershell
     .\Create-ADGroups.ps1 -CSVPath .\data\groups.csv
     ```

## Error Handling

The scripts include basic error handling to manage common issues such as:
- User or group already exists.
- Insufficient permissions.
- Invalid OU path.

If an error occurs, a detailed message will be logged in the `logs` directory.

## Logging

All operations performed by the scripts are logged for auditing and troubleshooting purposes. Logs are stored in the `logs` directory and include timestamps and detailed information about each operation.

## Contributing

We welcome contributions to improve these scripts. If you have suggestions for enhancements or find bugs, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contact

For any questions or further information, please contact [yourname@yourdomain.com](mailto:yourname@yourdomain.com).

---

By following these instructions, you can efficiently manage users and groups in your Active Directory environment using PowerShell. This README serves as a comprehensive guide to help you get started and utilize the scripts in this repository.
