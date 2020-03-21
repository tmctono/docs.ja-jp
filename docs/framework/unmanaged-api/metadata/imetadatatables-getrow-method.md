---
title: IMetaDataTables::GetRow メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177116"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="0d0d0-102">IMetaDataTables::GetRow メソッド</span><span class="sxs-lookup"><span data-stu-id="0d0d0-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="0d0d0-103">指定したテーブル インデックスのテーブル内の指定した行インデックスの行を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d0d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d0d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d0d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d0d0-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="0d0d0-106">[in]行の取得元となるテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="0d0d0-107">[in]取得する行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="0d0d0-108">[アウト]行へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d0d0-109">解説</span><span class="sxs-lookup"><span data-stu-id="0d0d0-109">Remarks</span></span>  

  <span data-ttu-id="0d0d0-110">このメソッドは一貫した結果を返さないため、このメソッドを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="0d0d0-111">GUID テーブルの詳細については、共通言語インフラストラクチャ (CLI) のドキュメント、特に「パーティション II: メタデータの定義とセマンティクス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="0d0d0-112">ドキュメントはオンラインで入手できます。[「ECMA C# および共通言語インフラストラクチャ標準](../../../standard/components.md#applicable-standards)と[標準 ECMA-335 - 共通言語インフラストラクチャ (CLI)」](http://www.ecma-international.org/publications/standards/Ecma-335.htm)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d0d0-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d0d0-113">Requirements</span></span>  
 <span data-ttu-id="0d0d0-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d0d0-115">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="0d0d0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d0d0-116">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d0d0-117">**.NET フレームワークのバージョン**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0d0-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0d0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d0d0-118">See also</span></span>

- [<span data-ttu-id="0d0d0-119">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d0d0-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0d0d0-120">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d0d0-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
