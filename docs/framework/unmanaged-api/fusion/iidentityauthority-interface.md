---
title: IIdentityAuthority インターフェイス
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609101"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="acfc7-102">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acfc7-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="acfc7-103">コード オブジェクトの id キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="acfc7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="acfc7-104">Methods</span></span>

|<span data-ttu-id="acfc7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="acfc7-105">Method</span></span>|<span data-ttu-id="acfc7-106">説明</span><span class="sxs-lookup"><span data-stu-id="acfc7-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="acfc7-107">2 つ指定されているかどうかを示す値を取得します[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)インスタンスが等しい。</span><span class="sxs-lookup"><span data-stu-id="acfc7-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="acfc7-108">2 つ指定されているかどうかを示す値を取得します[IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)インスタンスが等しい。</span><span class="sxs-lookup"><span data-stu-id="acfc7-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="acfc7-109">2 つの指定した文字列の定義 id の形式が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="acfc7-110">2 つの指定した文字列の参照 id の形式が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="acfc7-111">新しいポインターを取得します。 `IDefinitionIdentity` 、現在のスコープ内のコード オブジェクトを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="acfc7-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="acfc7-112">新しいポインターを取得します。 `IReferenceIdentity` 、現在のスコープ内のコード オブジェクトを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="acfc7-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="acfc7-113">指定した書式設定された文字列バージョンを取得`IDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="acfc7-114">指定した文字列形式を指定のワイド文字バッファーに設定`IDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="acfc7-115">示す値を取得するかどうか、指定した`IDefinitionIdentity`と`IReferenceIdentity`インスタンスが同じコード オブジェクトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfc7-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="acfc7-116">指定した文字列が同じコード オブジェクトを参照するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="acfc7-117">指定した文字列が新しく作成されたキーへのポインターを取得`IDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="acfc7-118">指定した文字列が新しく作成されたキーへのポインターを取得`IReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="acfc7-119">指定したハッシュ値を取得します。`IDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="acfc7-120">指定したハッシュ値を取得します。`IReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="acfc7-121">指定した書式設定された文字列バージョンを取得`IReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="acfc7-122">指定した文字列形式を指定のワイド文字バッファーに設定`IReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="acfc7-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="acfc7-123">インターフェイス ポインターを取得、`IDefinitionIdentity`書式指定文字列を指定された対象から生成されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="acfc7-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="acfc7-124">インターフェイス ポインターを取得、`IReferenceIdentity`書式指定文字列を指定された対象から生成されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="acfc7-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="acfc7-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="acfc7-125">Requirements</span></span>

<span data-ttu-id="acfc7-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfc7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="acfc7-127">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="acfc7-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="acfc7-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acfc7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="acfc7-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="acfc7-129">See also</span></span>

- [<span data-ttu-id="acfc7-130">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acfc7-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
