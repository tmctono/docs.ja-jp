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
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796427"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="aca66-102">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca66-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="aca66-103">コードオブジェクトの id キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="aca66-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="aca66-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="aca66-104">Methods</span></span>

|<span data-ttu-id="aca66-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="aca66-105">Method</span></span>|<span data-ttu-id="aca66-106">説明</span><span class="sxs-lookup"><span data-stu-id="aca66-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="aca66-107">指定した2つの[IDefinitionIdentity](idefinitionidentity-interface.md)インスタンスが等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="aca66-108">指定した2つの[IReferenceIdentity](ireferenceidentity-interface.md)インスタンスが等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="aca66-109">指定した2つの文字列定義 id 表現が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="aca66-110">指定した2つの文字列参照 id 表現が等しいかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="aca66-111">現在のスコープ内のコード`IDefinitionIdentity`オブジェクトを表す新しいインスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="aca66-112">現在のスコープ内のコード`IReferenceIdentity`オブジェクトを表す新しいインスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="aca66-113">指定したの書式設定され`IDefinitionIdentity`た文字列バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="aca66-114">指定したワイド文字バッファーに、指定`IDefinitionIdentity`したの文字列バージョンを格納します。</span><span class="sxs-lookup"><span data-stu-id="aca66-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="aca66-115">指定した`IDefinitionIdentity`と`IReferenceIdentity`インスタンスが同じコードオブジェクトを参照しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="aca66-116">指定した文字列が同じコードオブジェクトを参照しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="aca66-117">指定`IDefinitionIdentity`したに対して新しく作成された文字列キーへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="aca66-118">指定`IReferenceIdentity`したに対して新しく作成された文字列キーへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="aca66-119">指定した`IDefinitionIdentity`のハッシュ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="aca66-120">指定した`IReferenceIdentity`のハッシュ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="aca66-121">指定したの書式設定され`IReferenceIdentity`た文字列バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="aca66-122">指定したワイド文字バッファーに、指定`IReferenceIdentity`したの文字列バージョンを格納します。</span><span class="sxs-lookup"><span data-stu-id="aca66-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="aca66-123">指定した書式設定さ`IDefinitionIdentity`れた文字列から生成されたインスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="aca66-124">指定した書式設定さ`IReferenceIdentity`れた文字列から生成されたインスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca66-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="aca66-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="aca66-125">Requirements</span></span>

<span data-ttu-id="aca66-126">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aca66-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="aca66-127">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="aca66-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="aca66-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca66-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aca66-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="aca66-129">See also</span></span>

- [<span data-ttu-id="aca66-130">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca66-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
