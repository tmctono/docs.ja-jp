---
title: IMetaDataTables::GetUserStringHeapSize メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 1aea017f17e29544e9288e1f57e6f84f9a2f6dae
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501106"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="5c690-102">IMetaDataTables::GetUserStringHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="5c690-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="5c690-103">ユーザー文字列ヒープのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c690-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c690-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c690-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c690-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c690-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="5c690-106">入出力ユーザー文字列ヒープのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c690-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c690-107">要件</span><span class="sxs-lookup"><span data-stu-id="5c690-107">Requirements</span></span>  
 <span data-ttu-id="5c690-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c690-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c690-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="5c690-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c690-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c690-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c690-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c690-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c690-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c690-112">See also</span></span>

- [<span data-ttu-id="5c690-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c690-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="5c690-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c690-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
