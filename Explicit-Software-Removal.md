# Explicit Software Removal
```ps1
# Define a list of software to be removed by name (partial or full match)
$SoftwareToRemove = @(
    "Xbox",  # Replace with the name of the software you want to remove
    "Game Bar",  # Replace with the name of the software you want to remove
)

# Loop through the list of software and uninstall each item
foreach ($software in $SoftwareToRemove) {
    # Get the list of installed applications that match the name
    $installedApps = Get-WmiObject -Class Win32_Product | Where-Object {$_.Name -like "*$software*"}

    foreach ($app in $installedApps) {
        Write-Host "Removing: $($app.Name)"
        try {
            # Uninstall the software
            $app.Uninstall()  # This will uninstall the software
            Write-Host "$($app.Name) removed successfully."
        }
        catch {
            Write-Host "Failed to remove: $($app.Name). Error: $_"
        }
    }
}

# Remove UWP (Universal Windows Platform) Apps if necessary
$UwpAppsToRemove = @(
    "Microsoft.BingWeather",    # Replace with the UWP app name
    "Microsoft.GetHelp"         # Replace with the UWP app name
)

foreach ($uwpApp in $UwpAppsToRemove) {
    try {
        # Get the package and remove it
        Get-AppxPackage -Name $uwpApp | Remove-AppxPackage
        Write-Host "$uwpApp removed successfully."
    }
    catch {
        Write-Host "Failed to remove UWP app: $uwpApp. Error: $_"
    }
}

Write-Host "Software removal script completed."
