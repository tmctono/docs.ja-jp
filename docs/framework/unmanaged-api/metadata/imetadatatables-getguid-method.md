---
title: IMetaDataTables::GetGuid メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175279"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="f7cc0-102">IMetaDataTables::GetGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="f7cc0-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="f7cc0-103">指定したインデックス位置にある行から GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7cc0-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7cc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7cc0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7cc0-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="f7cc0-106">[in]GUID を取得する行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="f7cc0-107">[アウト]GUID へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7cc0-108">解説</span><span class="sxs-lookup"><span data-stu-id="f7cc0-108">Remarks</span></span>  

  <span data-ttu-id="f7cc0-109">このメソッドは一貫した結果を返さないため、このメソッドを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f7cc0-110">GUID テーブルの詳細については、共通言語インフラストラクチャ (CLI) のドキュメント、特に「パーティション II: メタデータの定義とセマンティクス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f7cc0-111">ドキュメントはオンラインで入手できます。[「ECMA C# および共通言語インフラストラクチャ標準](../../../standard/components.md#applicable-standards)と[標準 ECMA-335 - 共通言語インフラストラクチャ (CLI)」](http://www.ecma-international.org/publications/standards/Ecma-335.htm)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7cc0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7cc0-112">Requirements</span></span>  
 <span data-ttu-id="f7cc0-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7cc0-114">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="f7cc0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7cc0-115">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7cc0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7cc0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7cc0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7cc0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7cc0-117">See also</span></span>

- [<span data-ttu-id="f7cc0-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7cc0-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="f7cc0-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7cc0-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
