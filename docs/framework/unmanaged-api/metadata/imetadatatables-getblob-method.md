---
title: IMetaDataTables::GetBlob メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: f5a736d80f36afb8d0a643d4a4e36c9abff01995
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445432"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="53cbe-102">IMetaDataTables::GetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="53cbe-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="53cbe-103">指定した列インデックスにあるバイナリラージオブジェクト (BLOB) へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53cbe-104">構文</span><span class="sxs-lookup"><span data-stu-id="53cbe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53cbe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53cbe-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="53cbe-106">から`ppData`の取得元となるメモリアドレス。</span><span class="sxs-lookup"><span data-stu-id="53cbe-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="53cbe-107">入出力`ppData`のサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="53cbe-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="53cbe-108">入出力取得したバイナリデータへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="53cbe-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53cbe-109">要件</span><span class="sxs-lookup"><span data-stu-id="53cbe-109">Requirements</span></span>  
 <span data-ttu-id="53cbe-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53cbe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53cbe-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="53cbe-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53cbe-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53cbe-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53cbe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53cbe-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="53cbe-114">See also</span></span>

- [<span data-ttu-id="53cbe-115">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53cbe-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="53cbe-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53cbe-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
