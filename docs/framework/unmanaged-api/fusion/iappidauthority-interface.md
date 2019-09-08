---
title: IAppIdAuthority インターフェイス
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91ab2f71e7fb74f8e0e517b566d46d61c316ebe2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796842"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="e9d57-102">IAppIdAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9d57-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="e9d57-103">アプリケーション id と参照のキーを生成して比較するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9d57-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e9d57-104">Methods</span></span>  
  
|<span data-ttu-id="e9d57-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e9d57-105">Method</span></span>|<span data-ttu-id="e9d57-106">説明</span><span class="sxs-lookup"><span data-stu-id="e9d57-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="e9d57-107">指定した2つの[IDefinitionAppId](idefinitionappid-interface.md)インスタンスが等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="e9d57-108">フラグ値 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d57-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="e9d57-109">指定した2つの[IReferenceAppId](ireferenceappid-interface.md)インスタンスが等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="e9d57-110">フラグ値 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d57-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="e9d57-111">指定した2つの文字列定義が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="e9d57-112">フラグ値 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d57-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="e9d57-113">指定した2つの文字列参照が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="e9d57-114">フラグ値 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d57-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="e9d57-115">現在のスコープ内のアセンブリを表す`IDefinitionAppId` 、新しく生成されたインスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="e9d57-116">現在のスコープ内のアセンブリを表す`IReferenceAppId` 、新しく作成されたへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="e9d57-117">指定したフラグ値を使用`IDefinitionAppId`して、指定したの文字列バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="e9d57-118">指定した`IDefinitionAppId`と`IReferenceAppId`が同じアセンブリを表しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="e9d57-119">指定した定義文字列と参照文字列が同じアセンブリを表しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="e9d57-120">指定した`IDefinitionAppId`インスタンスを表す文字列キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="e9d57-121">指定した`IReferenceAppId`インスタンスを表す文字列キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="e9d57-122">指定した`IDefinitionAppId`インスタンスのハッシュキーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="e9d57-123">指定した`IReferenceAppId`インスタンスのハッシュキーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="e9d57-124">指定したフラグ値を使用`IReferenceAppId`して、指定したの文字列バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="e9d57-125">指定した文字列キーに`IDefinitionAppId`よって参照されるアセンブリを表すインスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="e9d57-126">指定した文字列キーに`IReferenceAppId`よって参照されるアセンブリを表すインスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d57-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9d57-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9d57-127">Requirements</span></span>  
 <span data-ttu-id="e9d57-128">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d57-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d57-129">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="e9d57-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e9d57-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d57-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d57-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9d57-131">See also</span></span>

- [<span data-ttu-id="e9d57-132">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9d57-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
