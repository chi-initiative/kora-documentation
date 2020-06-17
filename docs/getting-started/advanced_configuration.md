---
title: Advanced Configuration of Kora
---

# Advanced Configuration of Kora

This document explains advanced features of Kora, which may only be needed in certain circumstances.

## Using *mod_rewrite* in Kora

If your installation will exist at a URL with a subdirectory, it is important to adjust the ".htaccess" file inside of "public" to reflect this. **Note**: This is *only* applicable to a Kora installation accessible by subdirectory and *not* for one existing at a domain-level or subdomain-level URL. For an explanation of these circumstances, please see the ["Create Kora Installation URLs" part of the Reclaim/DoOO Installation guide](../installing_kora_domains/#create-kora-installation-urls).

1. If you have not yet done so, confirm that `mod_rewrite`. See "[Enabling *mod_rewrite*](../system_requirements/#enabling-mod_rewrite)" section of the "System Requirements" documentation.

2. Edit the ".htaccess" file inside the "public" directory.

    * If using a cPanel interface, follow the instructions for editing files in "[Upload and Prepare Kora Application Files via cPanel File Manager](../installing_kora_domains/#upload-and-prepare-kora-application-files-via-cpanel-file-manager)," a section in the Installation guide.

    * If using SSH or Terminal, navigate to "kora/public" and use `sudo nano`, this time to edit ".htaccess". An explanation for using `nano` with super user privileges is also contained in the "[Enabling *mod_rewrite*](../system_requirements/#enabling-mod_rewrite)" section of the "System Requirements" documentation.

    <span></span>

    The file's code will begin with:

        <IfModule mod_rewrite.c>
            <IfModule mod_negotiation.c>
                Options -MultiViews -Indexes
            </IfModule>

            RewriteEngine On
            #RewriteBase #add base url ex: www.website.com[/this part is your base url, the url subdirectory where you want your installation to be accessible from]
            #RewriteBase /your_base_url

3. Remove the `#` from the final line above and provide the subdirectory part of your URL for accessing your installation. For instance, if you installed Kora and created a symbolic link to a directory within your root called "kora", the last few lines might look like:

        RewriteEngine On
        #RewriteBase #add base url ex: www.website.com[/this part is your base url, the url subdirectory where you want your installation to be accessible from]
        RewriteBase /kora

4. Be sure to save your changes when exiting.



## Increasing Memory Usage and File Size Limits

A Kora installation relies on default values for memory and storage usage by PHP. However, these will be set too low to handle Kora installations where large files will be uploaded to the installation, such as high-resolution images, image-dense pdfs, or 3D objects with detailed surface texture files. To deal with this, the ".htaccess" file saved in the "public" directory contains a list of PHP attributes and associated increased values. In that file, they appear like this:

    #Recommended but only use these if your system allows overwrites
    #php_value upload_max_filesize 4998M
    #php_value post_max_size 4999M
    #php_value memory_limit 5000M
    #php_value max_execution_time 3000
    #php_value max_input_time 3000

If your server environment allows overwrites via the .htaccess file, simply edit this file and remove the `#` before each attribute to enable the overwrite. For editing instructions, see links to multiple explanations in the section above, "[Using *mod_rewrite* in Kora](#using-mod_rewrite-in-kora)".

In some cases however, such as in Domain of One's Own or other [Reclaim Hosting](https://reclaimhosting.com)-provided environments, these values cannot overwritten via this method. Instead, these values may be managed by the provided server graphical interface; in the case of Reclaim Hosting, this is the cPanel. In this example, these values are managed by a cPanel application called "MultiPHP INI Editor."

1. To adjust these values, begin by clicking on this application.

    <img style="display:block;margin:auto;max-width:100%" src="../getting-started-img/advanced_configuration_1_annotated.png" title="MultiPHP INI Editor">

2. Select the domain or subdomain where your installation is.

    <img style="display:block;margin:auto;max-width:100%" src="../getting-started-img/advanced_configuration_2_annotated.png" title="Select relevant domain or subdomain from the dropdown">

3. All of the overwritable PHP attributes for the selected domain or subdomain will appear; find each of those listed in the code block above and adjust their values as necessary. Be sure to save the new settings.
