---
title: IMetaDataTables2::GetMetaDataStorage メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: 55fcde6c47705e515eb2d20f25ac870e257b92c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501132"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="8e0e8-102">IMetaDataTables2::GetMetaDataStorage メソッド</span><span class="sxs-lookup"><span data-stu-id="8e0e8-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="8e0e8-103">指定したセクションに格納されているメタデータのサイズと内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="8e0e8-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e0e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e0e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e0e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e0e8-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="8e0e8-106">[入力、出力]メタデータセクションへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8e0e8-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="8e0e8-107">入出力メタデータストリームのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8e0e8-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e0e8-108">要件</span><span class="sxs-lookup"><span data-stu-id="8e0e8-108">Requirements</span></span>  
 <span data-ttu-id="8e0e8-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e0e8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e0e8-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8e0e8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e0e8-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e0e8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e0e8-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e0e8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e0e8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e0e8-113">See also</span></span>

- [<span data-ttu-id="8e0e8-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e0e8-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="8e0e8-115">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e0e8-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
