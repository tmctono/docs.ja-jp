---
title: NuGet パッケージの公開
description: .NET ライブラリを NuGet に公開するためのベスト プラクティスの推奨事項。
ms.date: 10/02/2018
ms.openlocfilehash: e567fe3f7e00bf322cdd50786e50128961107469
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706466"
---
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="d167d-103">NuGet パッケージの公開</span><span class="sxs-lookup"><span data-stu-id="d167d-103">Publishing a NuGet package</span></span>

<span data-ttu-id="d167d-104">NuGet パッケージは、パッケージ リポジトリから公開され、使用されます。</span><span class="sxs-lookup"><span data-stu-id="d167d-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="d167d-105">NuGet.org は最も広く知られ、使用されているリポジトリですが、NuGet パッケージを公開するための場所は数多くあります。</span><span class="sxs-lookup"><span data-stu-id="d167d-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="d167d-106">**[NuGet.org](https://www.nuget.org/)** は、NuGet パッケージの主要なオンライン リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="d167d-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="d167d-107">NuGet.org にあるパッケージはすべて一般に公開されています。</span><span class="sxs-lookup"><span data-stu-id="d167d-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="d167d-108">Visual Studio の既定のパッケージ ソースは NuGet.org です。また、多くの開発者にとって、やり取りする唯一のパッケージ リポジトリは NuGet.org です。</span><span class="sxs-lookup"><span data-stu-id="d167d-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="d167d-109">NuGet.org は、コミュニティからのフィードバックが必要な安定版パッケージとプレリリース パッケージを公開するのに最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="d167d-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="d167d-110">**[MyGet](https://myget.org/)** は、オープン ソース プロジェクト用のカスタム パッケージ フィードをサポートしているリポジトリ サービスです。</span><span class="sxs-lookup"><span data-stu-id="d167d-110">**[MyGet](https://myget.org/)** is a repository service that supports custom package feeds for open-source projects.</span></span> <span data-ttu-id="d167d-111">MyGet のパブリック カスタム フィードは、独自の CI サービスで作成したプレリリース パッケージを公開するのに理想的な場所です。</span><span class="sxs-lookup"><span data-stu-id="d167d-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="d167d-112">MyGet には商用のプライベート フィードも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d167d-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="d167d-113">**[ローカル フィード](/nuget/hosting-packages/local-feeds)** を使用すると、フォルダーをパッケージ リポジトリのように扱い、フォルダー内の `*.nupkg` ファイルを NuGet からアクセス可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d167d-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="d167d-114">ローカル フィードは、NuGet.org に公開する前に NuGet パッケージをテストする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d167d-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="d167d-115">NuGet.org では、一度アップロードしたら[パッケージを削除することはできません](/nuget/policies/deleting-packages)。</span><span class="sxs-lookup"><span data-stu-id="d167d-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="d167d-116">一般の UI から見えないようにパッケージを一覧から外すことはできますが、`*.nupkg` は引き続き復元でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d167d-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="d167d-117">また、nuget.org では、パッケージのバージョンを重複させることはできません。</span><span class="sxs-lookup"><span data-stu-id="d167d-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="d167d-118">エラーを含む NuGet パッケージを修正するには、正しくないパッケージを一覧から外し、バージョン番号をインクリメントして新しいバージョンのパッケージを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d167d-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="d167d-119">**✔️ 実行** コミュニティからのフィードバックが必要な[安定版パッケージとプレリリース パッケージを公開する](/nuget/create-packages/publish-a-package)場合、NuGet.org を選択します。</span><span class="sxs-lookup"><span data-stu-id="d167d-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="d167d-120">**✔️ 検討** 継続的インテグレーションによるビルドから、プレリリース パッケージを MyGet のフィードに公開します。</span><span class="sxs-lookup"><span data-stu-id="d167d-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="d167d-121">**✔️ 検討** ローカル フィードか MyGet を使用して、開発環境でパッケージをテストします。</span><span class="sxs-lookup"><span data-stu-id="d167d-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="d167d-122">パッケージの動作を確認したら、NuGet.org に公開します。</span><span class="sxs-lookup"><span data-stu-id="d167d-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="d167d-123">NuGet.org のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d167d-123">NuGet.org security</span></span>

<span data-ttu-id="d167d-124">悪意のあるユーザーが自分の NuGet アカウントにアクセスし、悪意のあるバージョンのライブラリをアップロードできないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="d167d-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="d167d-125">NuGet.org には、パッケージを公開する際の 2 要素認証と電子メールの通知が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d167d-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="d167d-126">NuGet.org にログインした後、 **[Account settings]\(アカウント設定\)** ページでこれらの機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d167d-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="d167d-127">![代替テキスト](./media/publish-nuget-package/nuget-2fa.png "NuGet アカウントのセキュリティ")</span><span class="sxs-lookup"><span data-stu-id="d167d-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="d167d-128">**✔️ 実行** Microsoft アカウントを使用して NuGet にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d167d-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="d167d-129">**✔️ 実行** NuGet へのアクセスに対して 2 要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d167d-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="d167d-130">**✔️ 実行** パッケージが公開されたときの電子メール通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d167d-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d167d-131">[前へ](sourcelink.md)
>[次へ](versioning.md)</span><span class="sxs-lookup"><span data-stu-id="d167d-131">[Previous](sourcelink.md)
[Next](versioning.md)</span></span>
