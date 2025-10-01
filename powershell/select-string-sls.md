# Select-String (sls)

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7.5" %}

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.5" %}

Alias value: `sls`

### Examples

{% code overflow="wrap" %}
```powershell
PS> reg query HKLM  /f <pattern> /t REG_SZ /s | Select-String -Pattern 'value'
PS> reg query HKLM  /f <pattern> /t REG_SZ /s | Select-String -Pattern 'val1|val2'
```
{% endcode %}

* `-Pattern`: Specifies the text to find on each line. The pattern value is treated as a regular expression. (refer to link **about\_Regular\_Expresions** above)

