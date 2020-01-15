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
ms.openlocfilehash: 9ac6eba18ae23dc80a8dc90383aa67cfe41b39ff
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937405"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="bd72c-102">IMetaDataTables::GetRow メソッド</span><span class="sxs-lookup"><span data-stu-id="bd72c-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="bd72c-103">指定したテーブルインデックスにあるテーブル内の指定した行インデックスにある行を取得します。</span><span class="sxs-lookup"><span data-stu-id="bd72c-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd72c-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd72c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd72c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd72c-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="bd72c-106">から行の取得元となるテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="bd72c-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="bd72c-107">から取得する行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="bd72c-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="bd72c-108">入出力行へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd72c-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd72c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd72c-109">Remarks</span></span>  

  <span data-ttu-id="bd72c-110">このメソッドは、一貫性のある結果を返さないため、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bd72c-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="bd72c-111">GUID テーブルの詳細については、共通言語基盤 (CLI) のドキュメント (特に「パーティション II: メタデータの定義とセマンティクス」) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd72c-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="bd72c-112">ドキュメントはオンラインで入手できます。「 [ecma C#および共通言語基盤の標準](../../../standard/components.md#applicable-standards)と[標準 ECMA-335-共通言語基盤 (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd72c-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd72c-113">要件</span><span class="sxs-lookup"><span data-stu-id="bd72c-113">Requirements</span></span>  
 <span data-ttu-id="bd72c-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd72c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd72c-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bd72c-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd72c-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd72c-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd72c-117">**.NET Framework のバージョン**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd72c-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd72c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd72c-118">See also</span></span>

- [<span data-ttu-id="bd72c-119">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd72c-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="bd72c-120">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd72c-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
