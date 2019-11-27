---
title: IMetaDataTables::GetUserString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 5936ca837c9ab452e992fcb09aacb476ab37316a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431435"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="41b2a-102">IMetaDataTables::GetUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="41b2a-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="41b2a-103">現在のスコープ内の文字列列にある、指定したインデックス位置にあるハードコーディングされた文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="41b2a-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="41b2a-104">構文</span><span class="sxs-lookup"><span data-stu-id="41b2a-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="41b2a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41b2a-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="41b2a-106">からハードコーディングされた文字列の取得元のインデックス値。</span><span class="sxs-lookup"><span data-stu-id="41b2a-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="41b2a-107">入出力`ppData`のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="41b2a-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="41b2a-108">入出力返された文字列へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="41b2a-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="41b2a-109">要件</span><span class="sxs-lookup"><span data-stu-id="41b2a-109">Requirements</span></span>

<span data-ttu-id="41b2a-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41b2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="41b2a-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="41b2a-111">**Header:** Cor.h</span></span>

<span data-ttu-id="41b2a-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="41b2a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="41b2a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41b2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41b2a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="41b2a-114">See also</span></span>

- [<span data-ttu-id="41b2a-115">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41b2a-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="41b2a-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41b2a-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
