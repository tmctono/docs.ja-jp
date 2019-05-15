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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4eaf426bc9c933de1d4b774928f2b0a54dfb472
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636941"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="5a071-102">IMetaDataTables::GetUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="5a071-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="5a071-103">現在のスコープ内で文字列の列で指定したインデックス位置には、ハード コーディングされた文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a071-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a071-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a071-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="5a071-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a071-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="5a071-106">[in]ハード コーディングされた文字列の取得元となるインデックス値。</span><span class="sxs-lookup"><span data-stu-id="5a071-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="5a071-107">[out]サイズへのポインター`ppData`します。</span><span class="sxs-lookup"><span data-stu-id="5a071-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="5a071-108">[out]返される文字列へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a071-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a071-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a071-109">Requirements</span></span>

<span data-ttu-id="5a071-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a071-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5a071-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a071-111">**Header:** Cor.h</span></span>

<span data-ttu-id="5a071-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="5a071-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="5a071-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a071-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5a071-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a071-114">See also</span></span>

- [<span data-ttu-id="5a071-115">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a071-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="5a071-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a071-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
