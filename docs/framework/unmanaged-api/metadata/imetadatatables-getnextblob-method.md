---
title: IMetaDataTables::GetNextBlob メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1e7181f50d94fa417bf9d00c3531747cefca82c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781476"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="9a033-102">IMetaDataTables::GetNextBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="9a033-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="9a033-103">テーブル内には、次のバイナリ ラージ オブジェクト (BLOB) のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a033-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a033-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a033-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a033-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a033-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="9a033-106">[in]Blob の列から返されるインデックス。</span><span class="sxs-lookup"><span data-stu-id="9a033-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="9a033-107">[out]次の BLOB のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9a033-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a033-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a033-108">Requirements</span></span>  
 <span data-ttu-id="9a033-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a033-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a033-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a033-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a033-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9a033-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a033-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a033-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a033-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a033-113">See also</span></span>

- [<span data-ttu-id="9a033-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a033-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="9a033-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a033-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
