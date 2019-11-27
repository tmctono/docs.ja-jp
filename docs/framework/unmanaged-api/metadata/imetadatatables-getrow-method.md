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
ms.openlocfilehash: 9973ef77a064dfe144d742d8cf12d8ae8dd2565f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447415"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="36c06-102">IMetaDataTables::GetRow メソッド</span><span class="sxs-lookup"><span data-stu-id="36c06-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="36c06-103">指定したテーブルインデックスにあるテーブル内の指定した行インデックスにある行を取得します。</span><span class="sxs-lookup"><span data-stu-id="36c06-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c06-104">構文</span><span class="sxs-lookup"><span data-stu-id="36c06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c06-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36c06-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="36c06-106">から行の取得元となるテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="36c06-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="36c06-107">から取得する行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="36c06-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="36c06-108">入出力行へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="36c06-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36c06-109">コメント</span><span class="sxs-lookup"><span data-stu-id="36c06-109">Remarks</span></span>  
 <span data-ttu-id="36c06-110">このメソッドは、一貫性のある結果を返さないため、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36c06-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="36c06-111">GUID テーブルの詳細については、共通言語基盤 (CLI) のドキュメント (特に「パーティション II: メタデータの定義とセマンティクス」) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c06-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="36c06-112">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c06-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c06-113">要件</span><span class="sxs-lookup"><span data-stu-id="36c06-113">Requirements</span></span>  
 <span data-ttu-id="36c06-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c06-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c06-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="36c06-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36c06-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="36c06-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36c06-117">**.NET Framework のバージョン**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c06-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c06-118">参照</span><span class="sxs-lookup"><span data-stu-id="36c06-118">See also</span></span>

- [<span data-ttu-id="36c06-119">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c06-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="36c06-120">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c06-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
