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
ms.openlocfilehash: 21ce66722e069573b651ada950b64ef6d97220fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501145"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="b8343-102">IMetaDataTables::GetUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="b8343-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="b8343-103">現在のスコープ内の文字列列にある、指定したインデックス位置にあるハードコーディングされた文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="b8343-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8343-104">構文</span><span class="sxs-lookup"><span data-stu-id="b8343-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="b8343-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8343-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="b8343-106">からハードコーディングされた文字列の取得元のインデックス値。</span><span class="sxs-lookup"><span data-stu-id="b8343-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="b8343-107">入出力のサイズへのポインター `ppData` 。</span><span class="sxs-lookup"><span data-stu-id="b8343-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="b8343-108">入出力返された文字列へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b8343-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8343-109">要件</span><span class="sxs-lookup"><span data-stu-id="b8343-109">Requirements</span></span>

<span data-ttu-id="b8343-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8343-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b8343-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="b8343-111">**Header:** Cor.h</span></span>

<span data-ttu-id="b8343-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8343-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="b8343-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8343-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b8343-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8343-114">See also</span></span>

- [<span data-ttu-id="b8343-115">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8343-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b8343-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8343-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
