---
title: IMetaDataEmit2::SaveDelta メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: d3e25f271fc434785e25e7b226ad98f86b5f8dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492786"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="53f4f-102">IMetaDataEmit2::SaveDelta メソッド</span><span class="sxs-lookup"><span data-stu-id="53f4f-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="53f4f-103">現在のエディットコンティニュセッションから、指定したファイルへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="53f4f-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f4f-104">構文</span><span class="sxs-lookup"><span data-stu-id="53f4f-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53f4f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53f4f-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="53f4f-106">から変更を保存するファイル名。</span><span class="sxs-lookup"><span data-stu-id="53f4f-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="53f4f-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="53f4f-107">[in] Reserved.</span></span> <span data-ttu-id="53f4f-108">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="53f4f-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f4f-109">要件</span><span class="sxs-lookup"><span data-stu-id="53f4f-109">Requirements</span></span>  
 <span data-ttu-id="53f4f-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53f4f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f4f-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="53f4f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53f4f-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="53f4f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53f4f-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53f4f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f4f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="53f4f-114">See also</span></span>

- [<span data-ttu-id="53f4f-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53f4f-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="53f4f-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53f4f-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
