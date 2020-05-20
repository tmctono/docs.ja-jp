---
title: Azure Active Directory
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 03f5ea8e84bc3c4a2a88a63d4b109aabf0c64f36
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614280"
---
# <a name="azure-active-directory"></a><span data-ttu-id="2706a-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2706a-103">Azure Active Directory</span></span>

<span data-ttu-id="2706a-104">Microsoft Azure Active Directory (Azure AD) は、id およびアクセス管理をサービスとして提供します。</span><span class="sxs-lookup"><span data-stu-id="2706a-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="2706a-105">お客様は、ユーザーの所有者、情報の保存先、その情報にアクセスできるユーザー、その情報を管理できるユーザー、およびアプリにアクセスできる対象を構成および管理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2706a-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="2706a-106">AAD は、シングルサインオン (SSO) エクスペリエンスを提供して、ユーザーを使用するように構成されたアプリケーションに対してユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="2706a-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="2706a-107">独自に使用することも、オンプレミスで実行されている Windows AD と統合することもできます。</span><span class="sxs-lookup"><span data-stu-id="2706a-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="2706a-108">Azure AD はクラウド用に構築されています。</span><span class="sxs-lookup"><span data-stu-id="2706a-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="2706a-109">これは、LDAP を使用する Windows AD とは異なり、REST ベースの Graph API とクエリに OData 構文を使用するクラウドネイティブの id ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="2706a-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="2706a-110">オンプレミス Active Directory では、Id 同期サービスを使用してユーザー属性をクラウドに同期させることができます。これにより、Azure AD を使用して、すべての認証をクラウドで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2706a-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="2706a-111">または、オンプレミスの Windows AD によって実行される ADFS 経由でローカル Active Directory に渡すために、Connect を使用して認証を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2706a-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="2706a-112">Azure AD は、オンプレミスでホストされているアプリケーションに SSO を提供するために使用される会社ブランドのサインイン画面、マルチファクトリ認証、およびクラウドベースのアプリケーションプロキシをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2706a-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="2706a-113">さまざまな種類のセキュリティレポートとアラート機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2706a-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="2706a-114">References</span><span class="sxs-lookup"><span data-stu-id="2706a-114">References</span></span>

- [<span data-ttu-id="2706a-115">Microsoft ID プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2706a-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="2706a-116">[前へ](authentication-authorization.md)
>[次へ](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="2706a-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
