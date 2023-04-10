# ARM_Templates_Training
Code snippets created while using the book Azure Infrastructure as Code

# Links
- [Book - O'Reilly - Azure Infrastructure as Code](https://learning.oreilly.com/library/view/azure-infrastructure-as/9781617299421/)
- [Microsoft Course](Validate Azure resources by using the ARM Template Test Toolkit)
- [Test Tool Kit Instructions](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/test-toolkit)
- [Test Tool Kit Scripts](https://aka.ms/arm-ttk-latest)

# Notes
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

