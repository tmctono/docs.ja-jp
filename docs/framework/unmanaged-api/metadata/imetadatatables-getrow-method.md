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
ms.openlocfilehash: 13d514157382c75a2eb9799837f9355d0e469c99
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489913"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="54afd-102">IMetaDataTables::GetRow メソッド</span><span class="sxs-lookup"><span data-stu-id="54afd-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="54afd-103">指定したテーブルインデックスにあるテーブル内の指定した行インデックスにある行を取得します。</span><span class="sxs-lookup"><span data-stu-id="54afd-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54afd-104">構文</span><span class="sxs-lookup"><span data-stu-id="54afd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54afd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54afd-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="54afd-106">から行の取得元となるテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="54afd-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="54afd-107">から取得する行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="54afd-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="54afd-108">入出力行へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="54afd-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54afd-109">解説</span><span class="sxs-lookup"><span data-stu-id="54afd-109">Remarks</span></span>  

  <span data-ttu-id="54afd-110">このメソッドは、一貫性のある結果を返さないため、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54afd-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="54afd-111">GUID テーブルの詳細については、共通言語基盤 (CLI) のドキュメント (特に「パーティション II: メタデータの定義とセマンティクス」) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54afd-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="54afd-112">ドキュメントはオンラインで入手できます。「 [Ecma C# および共通言語基盤の標準](../../../standard/components.md#applicable-standards)と[標準 ecma-335-共通言語基盤 (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54afd-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54afd-113">要件</span><span class="sxs-lookup"><span data-stu-id="54afd-113">Requirements</span></span>  
 <span data-ttu-id="54afd-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54afd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54afd-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="54afd-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54afd-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="54afd-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54afd-117">**.NET Framework のバージョン**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54afd-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54afd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="54afd-118">See also</span></span>

- [<span data-ttu-id="54afd-119">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54afd-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="54afd-120">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54afd-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
