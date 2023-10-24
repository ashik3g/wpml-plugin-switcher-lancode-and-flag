# wpml-plugin-switcher-lancode-and-flag
WPML Plugin by Default not providing Switcher Flag and Language Code, we solve using that filter.

# Custom WPML Language Switcher for WordPress

The function `custom_language_names` aims to modify the `translated_name` property of each language. Depending on the active theme, plugins, or the version of WPML in use, the output may not be as desired. 

## Steps to Modify the Language Switcher

### 1. Adjusting the Language Names with WPML's Filter

WPML offers a filter named `icl_ls_languages` that lets you adjust the output of the language switcher. The code below adjusts the displayed names of the languages: functions.php

```php
function custom_language_names($languages) {
    foreach ($languages as $lang_code => &$language) {
        $language['native_name'] = strtoupper($lang_code);
    }
    return $languages;
}
add_filter('icl_ls_languages', 'custom_language_names');
```

### 2. Configuring WPML Language Switcher Display:
Navigate to WPML -> Languages.
Find the section for the Menu language switcher or Widget language switcher (based on where you're displaying it).
Make sure to select either "Language name in the current language" or "Native language name".

### 3. Troubleshooting Potential Conflicts
At times, other plugins or themes might conflict with WPML's functionalities. Here's how you can diagnose such issues:

Temporarily deactivate all other plugins.
Switch to a basic WordPress theme (like Twenty Twenty-One).
Check if the function works as expected.
If the function works after these steps, you can reactivate the plugins one by one to identify the one causing the conflict.

🎉 Thank you for reading! Enjoy implementing these changes and making the most out of your WPML setup! 🎉
