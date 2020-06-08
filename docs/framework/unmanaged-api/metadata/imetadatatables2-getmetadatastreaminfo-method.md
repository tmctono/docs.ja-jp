---
title: IMetaDataTables2::GetMetaDataStreamInfo メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 7d39d089c348b7320651ed21ea14ba07d7877fd4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501096"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="4230e-102">IMetaDataTables2::GetMetaDataStreamInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="4230e-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="4230e-103">指定したインデックス位置にあるメタデータストリームの名前、サイズ、および内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="4230e-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4230e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4230e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4230e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4230e-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="4230e-106">から要求されたメタデータストリームのインデックス。</span><span class="sxs-lookup"><span data-stu-id="4230e-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="4230e-107">入出力ストリームの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4230e-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="4230e-108">入出力メタデータストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4230e-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="4230e-109">入出力のサイズ (バイト単位) `ppv` 。</span><span class="sxs-lookup"><span data-stu-id="4230e-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4230e-110">要件</span><span class="sxs-lookup"><span data-stu-id="4230e-110">Requirements</span></span>  
 <span data-ttu-id="4230e-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4230e-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4230e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4230e-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4230e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4230e-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4230e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4230e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4230e-115">See also</span></span>

- [<span data-ttu-id="4230e-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4230e-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="4230e-117">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4230e-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
