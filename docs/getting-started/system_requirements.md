# System Requirements

Kora requires a server environment deployed with what is often referred to as a LAMP Stack. LAMP stands for:

* Linux
* Apache
* MySQL
* PHP

In order to install Kora, the minimum version of **MySQL needed is 5.7.20** and the minimum version of **PHP is 7.1.3**. Oftentimes, the server environment will rely on minor variations of these. For instance, the HTTPD (or Hypertext Transfer Protocol Daemon) version of Apache is often used.

Use whichever installer is available for your Linux-based environment to install — or confirm installation of — these basic applicaitons. Common installers are `apt` (Advanced Package Tool) and `yum` (Yellowdog Updater, Modifier).

## PHP Packages

After confirming the environment is a LAMP Stack with the appropriate version levels for MySQL and PHP, it will be important to install several additional PHP packages. These are:

<table style="width:100%;text-align:center">
    <tr>
        <td> php-common</td>
        <td> php-mysql</td>
        <td> php-xml</td>
    </tr>
    <tr>
        <td> php-xmlrpc </td>
        <td> php-curl </td>
        <td> php-gd </td>
    </tr>
    <tr>
        <td> php-imagick </td>
        <td> php-cli </td>
        <td> php-dev </td>
    </tr>
    <tr>
        <td> php-imap </td>
        <td> php-mbstring </td>
        <td> php-opcache </td>
    </tr>
    <tr>
        <td> php-soap </td>
        <td> php-zip </td>
        <td> php-intl</td>
    </tr>
</table>
<span style="clear:both"></span>

Install the versions of these packages that correspond to the version of PHP you have installed as a part of your LAMP Stack.

## HTTPS and SSL certificate

Kora requires the HTTPS protocol to be enabled for the domain in which it is accessible, which requires an SSL certificate. For some server environments, the included interface — such as cPanel — will have a section for managing the process of enabling HTTPS and acquiring/associating an SSL certificate as a part of that process. Sometimes — such as with MSU's Domains of One's Own accounts and their corresponding cPanel — the SSL certificate and its renewal are handled behind-the-scenes, so to speak, and the certificate is aquired/associated when the HTTPS protocol option is enabled.

In other instances, it will be necessary to apply for an SSL certificate. This can be done in a number of ways, but the one most commonly used as a cost-free method is through a server application called [Certbot](https://certbot.eff.org/about), which manages the application, acquisition, and association of an SSL certificate from a free certificate supplier called [Let's Encrypt](https://letsencrypt.org/about/). Certbot is a great option for those who need to go this route because it can also be configured to handle automatic certification renewals, since SSL certificates expire. One possible way to install certbot into your server environment is from Certbot directly, and then to provide "Execute" permissions.

        wget https://dl.eff.org/certbot-auto
<span style="clear:both"></span>

        chmod a+x certbot-auto

The specifics of using certbot will depend upon your domain, email address, etc. so it wouldn't be possible to provide a guide here. Certbot provides some more-granular instructions for use on [their "Instructions" page](https://certbot.eff.org/instructions), which should be enough to get the SSL certificate needed.

## Kora Email

Kora requires a Simple Mail transfer Protocol (SMTP) email server for sending emails related to new user sign-ups, invitations, or lost passwords. In some cases, the email server will be handled by some part of the included interface — including in many cPanel-based interfaces — but in others the email server may be managed via the SSH connection to the environment. When configuring Kora's email settings, it is possible to use an SMTP server on another domain, by providing the appropriate domain name for the server for "Mail Host," appropriate user email address from that server for "Mail User," and the email address's password in "Mail Password." Please see Step 5 of "[Set Up Server Email and Link It to Kora](../installing_kora_domains/#set-up-server-email-and-link-it-to-kora)." Additionally, if the "Mail User" and "Mail From Address" do not match, the recipient's mail client is more likely to flag the generated email as spam.

In the case of MSU's Domains of one's Own, emails have been entirely disabled to comply with a univeristy-wide policy. If you are unable to set up an SMTP server to use with your Kora installation — such as on another, privately-managed domain — you will need to manage user creation and password resets manually. To do this, please consult the guide for [manually managing Kora user accounts](../../user-accounts/managing_users_in_a_kora_installation/#manual-user-confirmationsactivations-and-password-resets).
