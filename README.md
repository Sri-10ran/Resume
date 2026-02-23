Get-ChildItem -Recurse -Exclude *.jpg,*.jpeg,*.png,*.gif,*.bmp,*.svg,*.webp,*.ico | 
    ForEach-Object {
        $depth = ($_.FullName.Split('\').Count - (Get-Location).Path.Split('\').Count)
        $indent = "   " * $depth
        $indent + $_.Name
    } > folder_structure.txt
