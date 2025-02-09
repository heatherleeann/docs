---
title: À propos de SAML pour la gestion des identités et des accès d’entreprise
shortTitle: About SAML for IAM
intro: 'Vous pouvez utiliser l’authentification unique SAML {% ifversion ghae %}et SCIM (System for Cross-domain Identity Management) {% endif %}pour gérer de façon centralisée l’accès aux organisations {% ifversion ghec %}appartenant à votre entreprise {% data variables.product.prodname_dotcom_the_website %}{% elsif ghes %}à {% data variables.location.product_location %}{% elsif ghae %}à {% data variables.location.product_location %}{% endif %}.'
versions:
  ghec: '*'
  ghes: '*'
  ghae: '*'
type: overview
topics:
  - Accounts
  - Access management
  - Authentication
  - Enterprise
  - Identity
redirect_from:
  - /admin/authentication/about-identity-and-access-management-for-your-enterprise
  - /github/setting-up-and-managing-your-enterprise/about-identity-and-access-management-for-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise/configuring-identity-and-access-management-for-your-enterprise-account/about-identity-and-access-management-for-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise/about-user-provisioning-for-organizations-in-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise/configuring-saml-single-sign-on-and-scim-for-your-enterprise-account-using-okta
  - /admin/authentication/managing-identity-and-access-for-your-enterprise/about-identity-and-access-management-for-your-enterprise
  - /admin/identity-and-access-management/managing-iam-for-your-enterprise/about-identity-and-access-management-for-your-enterprise
  - /admin/identity-and-access-management/using-saml-for-enterprise-iam/about-identity-and-access-management-for-your-enterprise
ms.openlocfilehash: d719ef81948cef75018b0976fc97ef45c267469f
ms.sourcegitcommit: c562c85cc75ffe1eb4e9595d8adc09ec71697ab1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2022
ms.locfileid: '148180028'
---
## À propos de l’authentification unique SAML pour {% ifversion ghec or ghae %}votre entreprise sur {% endif %}{% ifversion ghec or ghes %}{% data variables.location.product_location %}{% elsif ghae %}{% data variables.product.product_name %}{% endif %}

{% ifversion ghec %}

Si les membres de votre entreprise gèrent leurs propres comptes d’utilisateur sur {% data variables.location.product_location %}, vous pouvez configurer l’authentification SAML comme restriction d’accès supplémentaire pour votre entreprise ou votre organisation. {% data reusables.saml.dotcom-saml-explanation %} 

{% data reusables.saml.saml-accounts %}

{% data reusables.saml.about-saml-enterprise-accounts %} Pour plus d’informations, consultez « [Configuration d’une authentification unique (SSO) SAML pour votre entreprise](/admin/authentication/managing-identity-and-access-for-your-enterprise/configuring-saml-single-sign-on-for-your-enterprise). »

Vous pouvez également provisionner et gérer les comptes des membres de votre entreprise avec {% data variables.product.prodname_emus %}. Pour vous aider à déterminer si l’authentification unique SAML ou {% data variables.product.prodname_emus %} constitue la meilleure solution pour votre entreprise, consultez « [À propos de l’authentification pour votre entreprise](/admin/identity-and-access-management/managing-iam-for-your-enterprise/about-authentication-for-your-enterprise#identifying-the-best-authentication-method-for-your-enterprise) ».

{% data reusables.enterprise-accounts.about-recovery-codes %} Pour plus d’informations, consultez « [Gestion des codes de récupération pour votre entreprise](/admin/identity-and-access-management/managing-recovery-codes-for-your-enterprise) ».

Après avoir activé l’authentification unique SAML, selon le fournisseur d’identité que vous utilisez, vous pouvez activer des fonctionnalités de gestion des identités et des accès supplémentaires. 

Si vous utilisez Azure AD comme fournisseur d’identité, vous pouvez utiliser la synchronisation d’équipe pour gérer l’appartenance à l’équipe au sein de chaque organisation. {% data reusables.identity-and-permissions.about-team-sync %} Pour plus d’informations, consultez « [Gestion de la synchronisation d’équipe pour les organisations dans votre compte d’entreprise](/admin/authentication/managing-identity-and-access-for-your-enterprise/managing-team-synchronization-for-organizations-in-your-enterprise) ».

{% note %}

**Remarque :** Vous ne pouvez pas utiliser SCIM au niveau de l’entreprise, sauf si votre entreprise est activée pour {% data variables.product.prodname_emus %}.

{% endnote %}

{% data reusables.saml.switching-from-org-to-enterprise %} Pour plus d’informations, consultez « [Basculement de votre configuration SAML d’une organisation vers un compte d’entreprise](/github/setting-up-and-managing-your-enterprise/configuring-identity-and-access-management-for-your-enterprise-account/switching-your-saml-configuration-from-an-organization-to-an-enterprise-account) ».

{% elsif ghes %}

L’authentification unique SAML permet aux utilisateurs de s’authentifier et d’accéder à {% data variables.location.product_location %} via un système externe de gestion des identités.

SAML est un standard basé sur XML pour l’authentification et l’autorisation. Quand vous configurez SAML pour {% data variables.location.product_location %}, le système externe d’authentification s’appelle un fournisseur d’identité (IdP). Votre instance fait office de fournisseur de service SAML. Pour plus d’informations sur la norme SAML, consultez [Security Assertion Markup Language](https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language) sur Wikipédia.

Pour plus d’informations sur la configuration de l’authentification unique SAML sur {% data variables.product.product_name %}, consultez « [Configuration de l’authentification unique SAML pour votre entreprise](/admin/identity-and-access-management/using-saml-for-enterprise-iam/configuring-saml-single-sign-on-for-your-enterprise) ».

{% data reusables.saml.saml-ghes-account-revocation %}

{% data reusables.enterprise_user_management.external_auth_disables_2fa %}

{% data reusables.enterprise_user_management.built-in-authentication %}

{% elsif ghae %}

{% data reusables.saml.ae-uses-saml-sso %} {% data reusables.saml.ae-enable-saml-sso-during-bootstrapping %}

Après avoir configuré l’application pour {% data variables.product.product_name %} sur votre IdP, vous pouvez provisionner l’accès à {% data variables.location.product_location %} en affectant l’application aux utilisateurs et groupes sur votre IdP. Pour plus d’informations sur l’authentification unique SAML pour {% data variables.product.product_name %}, consultez « [Configuration de l’authentification unique SAML pour votre entreprise](/admin/authentication/configuring-saml-single-sign-on-for-your-enterprise) ».

{% data reusables.scim.after-you-configure-saml %} Pour plus d’informations, consultez « [Configuration de l’approvisionnement d’utilisateurs pour votre entreprise](/admin/authentication/configuring-user-provisioning-for-your-enterprise) ».

Pour savoir comment configurer l’authentification et le provisionnement d’utilisateurs pour {% data variables.location.product_location %} avec votre IdP spécifique, consultez « [Configuration de l’authentification et du provisionnement avec votre fournisseur d’identité](/admin/authentication/configuring-authentication-and-provisioning-with-your-identity-provider) ».

{% endif %}

## Fournisseurs d’identité pris en charge

{% ifversion ghec %}

Nous testons et prenons officiellement en charge les fournisseurs d’identité suivants. Pour l’authentification unique SAML, nous offrons une prise en charge limitée pour tous les fournisseurs d’identité qui implémentent la norme SAML 2.0. Pour plus d’informations, consultez le [Wiki SAML](https://wiki.oasis-open.org/security) sur le site web OASIS.

Fournisseur d’identité | SAML | Synchronisation d’équipe | 
--- | :--: | :-------: |
Active Directory Federation Services (AD FS) | {% octicon "check-circle-fill" aria-label= "The check icon" %} | |
Azure Active Directory (Azure AD) | {% octicon "check-circle-fill" aria-label="The check icon" %} | {% octicon "check-circle-fill" aria-label="The check icon" %} |
Okta | {% octicon "check-circle-fill" aria-label="The check icon" %} | |
OneLogin | {% octicon "check-circle-fill" aria-label="The check icon" %} | |
PingOne | {% octicon "check-circle-fill" aria-label="The check icon" %} | |
Shibboleth | {% octicon "check-circle-fill" aria-label="The check icon" %} | |

{% elsif ghes %}

{% data reusables.saml.saml-supported-idps %}

{% ifversion ghes > 3.3 %}

Si votre IdP prend en charge les assertions chiffrées, vous pouvez configurer des assertions chiffrées sur {% data variables.product.product_name %} pour renforcer la sécurité durant le processus d’authentification.

{% endif %}

{% data reusables.saml.saml-single-logout-not-supported %}

{% elsif ghae %}

Les fournisseurs d’identité suivants sont officiellement pris en charge pour l’intégration à {% data variables.product.prodname_ghe_managed %}.

{% data reusables.saml.okta-ae-sso-beta %}

{% data reusables.github-ae.saml-idp-table %}

{% endif %}

{% ifversion ghae %}

## Mappage des équipes {% data variables.product.prodname_ghe_managed %} aux groupes Okta

Si vous utilisez Okta en tant que fournisseur d’identité, vous pouvez mapper vos groupes Okta aux équipes sur {% data variables.product.product_name %}. Pour plus d’informations, consultez « [Mappage de groupes Okta à des équipes](/admin/authentication/configuring-authentication-and-provisioning-with-your-identity-provider/mapping-okta-groups-to-teams) ».

{% endif %}

## Pour aller plus loin

- [Wiki SAML](https://wiki.oasis-open.org/security) sur le site web OASIS
- [Système de gestion des identités inter-domaines : protocole (RFC 7644)](https://tools.ietf.org/html/rfc7644) sur le site web IETF {%- ifversion ghae %}
- « [Restriction du trafic réseau vers votre entreprise avec une liste d’adresses IP autorisées](/admin/configuration/configuring-your-enterprise/restricting-network-traffic-to-your-enterprise-with-an-ip-allow-list) » {%- endif %}
