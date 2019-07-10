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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fc95c618a7a06f5e6c219d7707af291770c06a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781407"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="96354-102">IMetaDataTables::GetRow メソッド</span><span class="sxs-lookup"><span data-stu-id="96354-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="96354-103">指定したテーブルのインデックス位置にある表に、指定した行インデックス位置にある行を取得します。</span><span class="sxs-lookup"><span data-stu-id="96354-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96354-104">構文</span><span class="sxs-lookup"><span data-stu-id="96354-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96354-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96354-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="96354-106">[in]行の取得元となるテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="96354-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="96354-107">[in]取得する行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="96354-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="96354-108">[out]行へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="96354-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96354-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="96354-109">Remarks</span></span>  
 <span data-ttu-id="96354-110">お勧めしません、このメソッドを使用して一貫性のある結果を返さないためです。</span><span class="sxs-lookup"><span data-stu-id="96354-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="96354-111">GUID の表については、ドキュメントを参照して、共通言語基盤 (CLI)、特に"第 2 部。メタデータの定義およびセマンティクス"。</span><span class="sxs-lookup"><span data-stu-id="96354-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="96354-112">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96354-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96354-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="96354-113">Requirements</span></span>  
 <span data-ttu-id="96354-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96354-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96354-115">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96354-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96354-116">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="96354-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96354-117">**.NET framework のバージョン**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96354-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96354-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="96354-118">See also</span></span>

- [<span data-ttu-id="96354-119">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96354-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="96354-120">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96354-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
