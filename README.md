# ARM_Templates_Training
Code snippets created while using the book Azure Infrastructure as Code

# Prerequisites
- Install ARM & BICEP extensions on VSCode
- 
# Links
- [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates/tree/master/quickstarts)
- [Book - O'Reilly - Azure Infrastructure as Code](https://learning.oreilly.com/library/view/azure-infrastructure-as/9781617299421/)
- [Define resources with Bicep, ARM templates, and Terraform AzAPI provider](https://learn.microsoft.com/en-nz/azure/templates/)
- [Microsoft Course](Validate Azure resources by using the ARM Template Test Toolkit)
- [Test Tool Kit Instructions](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/test-toolkit)
- [Test Tool Kit Scripts](https://aka.ms/arm-ttk-latest)

# ARM Templates
## create_storage_and_container.json
```
az deployment group create \
  --resource-group rg-arm-templates-test \
  --template-file create_storage_and_container.json
```

## Azure SQL database in an existing server
```
az deployment group create \
  --resource-group person-selector-rg \
  --template-file create_db_on_existing_server.json \
  --parameters create_db_on_existing_server.parameters.json
```
### Create a table & insert rows
```

CREATE TABLE Person
(
    PersonId INT IDENTITY PRIMARY KEY,
    FirstName NVARCHAR(128) NOT NULL,
    MiddelInitial NVARCHAR(10),
    LastName NVARCHAR(128) NOT NULL,
    DateOfBirth DATE NOT NULL
)

INSERT INTO [dbo].[Person](FirstName, MiddelInitial, LastName, DateOfBirth)
VALUES ('Rajesh', 'V', 'Babu', '8/2/06')

INSERT INTO [dbo].[Person](FirstName, MiddelInitial, LastName, DateOfBirth)
VALUES ('Maya', 'M', 'Babu', '9/2/06')

```


# Testing Notes
- If you on MacOS
    - Dont have powershell installed : 
        - brew install cooreutils
        - brew install --cask powershell
    - Get shells TTK
        - git clone https://github.com/Azure/arm-ttk.git
    - To start : 
        - pwsh
        - Import-Module ./arm-template-toolkit/arm-ttk/arm-ttk.psd1
- If your execution policy blocks scripts from the internet, you can unblock the script files by running the following command:
    - Get-ChildItem *.ps1, *.psd1, *.ps1xml, *.psm1 -Recurse | Unblock-File

# Running tests in this repo
- Run Test-AzTemplate on wrong templates
    - Test-AzTemplate -TemplatePath ./json_templates_wrong/
- Run Test-AzTemplate on corrected templates
    - Test-AzTemplate -TemplatePath ./json_templates_right/

