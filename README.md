# CI_CD_PowerBI


Steps to enable Azure AD SSO for GitHub:
GitHub Enterprise Cloud or Enterprise Server is required to use SSO with Azure AD (GitHub Free for individuals does not support this).

In Azure Portal, register GitHub as an enterprise application.

Configure the SAML or OIDC settings to connect Azure AD with GitHub.

In GitHub Organization settings, enable SAML SSO and connect it to your Azure AD tenant.

Assign users/groups in Azure AD to the GitHub enterprise application.

Optionally, enforce SSO enforcement policies on your GitHub org.
