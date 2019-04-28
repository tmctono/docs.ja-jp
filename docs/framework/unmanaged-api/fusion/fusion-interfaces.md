---
title: Fusion インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec2fd3b309820f2bfb7f6091cc3db720db497408
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697668"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="6fcf8-102">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-102">Fusion Interfaces</span></span>
<span data-ttu-id="6fcf8-103">このセクションでは、fusion API がアプリケーションのリソースのプロパティにアクセスして、アプリケーションのリソースの正しいバージョンを見つけるために使用するアンマネージ インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6fcf8-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6fcf8-104">In This Section</span></span>  
 [<span data-ttu-id="6fcf8-105">IAppIdAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="6fcf8-106">アプリケーション id と参照キーの比較を生成するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="6fcf8-107">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="6fcf8-108">グローバル アセンブリ キャッシュの表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6fcf8-109">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="6fcf8-110">グローバル アセンブリ キャッシュ内の 1 つのアセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6fcf8-111">IAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="6fcf8-112">配列の列挙子を表す`IAssemblyName`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="6fcf8-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="6fcf8-114">記述して、アセンブリの一意の id の操作のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="6fcf8-115">IDefinitionAppId インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="6fcf8-116">現在のスコープ内でアプリケーションを定義するコードの一意の識別子を表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="6fcf8-117">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="6fcf8-118">現在のスコープ内でアプリケーションを定義するコードの一意のシグネチャを表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="6fcf8-119">IEnumDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="6fcf8-120">コレクションの列挙子として機能`IDefinitionIdentity`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="6fcf8-121">IEnumIDENTITY_ATTRIBUTE インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="6fcf8-122">現在のスコープ内のコード オブジェクトの属性の列挙子として機能します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="6fcf8-123">IEnumReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="6fcf8-124">コレクションの列挙子として機能`IReferenceIdentity`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="6fcf8-125">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="6fcf8-126">コード オブジェクトの id キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="6fcf8-127">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="6fcf8-128">グローバル アセンブリ キャッシュにインストールされている参照先アセンブリの列挙子を表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6fcf8-129">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="6fcf8-130">グローバル アセンブリ キャッシュにインストールされている項目を表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6fcf8-131">IReferenceAppId インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="6fcf8-132">現在のスコープ内でアプリケーションの一意の識別子への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="6fcf8-133">IReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fcf8-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="6fcf8-134">コード オブジェクトの一意のシグネチャへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="6fcf8-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6fcf8-135">参照</span><span class="sxs-lookup"><span data-stu-id="6fcf8-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="6fcf8-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fcf8-136">Related Sections</span></span>  
 [<span data-ttu-id="6fcf8-137">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="6fcf8-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="6fcf8-138">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="6fcf8-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="6fcf8-139">Fusion 構造体</span><span class="sxs-lookup"><span data-stu-id="6fcf8-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
