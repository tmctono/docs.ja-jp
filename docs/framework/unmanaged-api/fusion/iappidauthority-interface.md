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
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127130"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="00746-102">IAppIdAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00746-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="00746-103">アプリケーション id と参照のキーを生成して比較するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="00746-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00746-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="00746-104">Methods</span></span>  
  
|<span data-ttu-id="00746-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="00746-105">Method</span></span>|<span data-ttu-id="00746-106">説明</span><span class="sxs-lookup"><span data-stu-id="00746-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="00746-107">指定した2つの[IDefinitionAppId](idefinitionappid-interface.md)インスタンスが等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="00746-108">フラグ値 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="00746-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="00746-109">指定した2つの[IReferenceAppId](ireferenceappid-interface.md)インスタンスが等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="00746-110">フラグ値 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="00746-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="00746-111">指定した2つの文字列定義が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="00746-112">フラグ値 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="00746-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="00746-113">指定した2つの文字列参照が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="00746-114">フラグ値 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION を渡して、それぞれのバージョン情報を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="00746-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="00746-115">現在のスコープ内のアセンブリを表す、新しく生成された `IDefinitionAppId` インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="00746-116">現在のスコープ内のアセンブリを表す、新しく作成された `IReferenceAppId` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="00746-117">指定したフラグ値を使用して、指定した `IDefinitionAppId`の文字列バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="00746-118">指定した `IDefinitionAppId` と `IReferenceAppId` が同じアセンブリを表しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="00746-119">指定した定義文字列と参照文字列が同じアセンブリを表しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="00746-120">指定された `IDefinitionAppId` インスタンスを表す文字列キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="00746-121">指定された `IReferenceAppId` インスタンスを表す文字列キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="00746-122">指定された `IDefinitionAppId` インスタンスのハッシュキーを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="00746-123">指定された `IReferenceAppId` インスタンスのハッシュキーを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="00746-124">指定したフラグ値を使用して、指定した `IReferenceAppId`の文字列バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="00746-125">指定した文字列キーによって参照されるアセンブリを表す `IDefinitionAppId` インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="00746-126">指定した文字列キーによって参照されるアセンブリを表す `IReferenceAppId` インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="00746-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00746-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="00746-127">Requirements</span></span>  
 <span data-ttu-id="00746-128">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00746-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00746-129">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="00746-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="00746-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00746-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00746-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="00746-131">See also</span></span>

- [<span data-ttu-id="00746-132">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00746-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
