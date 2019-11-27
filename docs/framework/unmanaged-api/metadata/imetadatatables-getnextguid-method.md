---
title: IMetaDataTables::GetNextGuid メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
ms.openlocfilehash: 32edbb6a0eeaf636338983c5cc2e032ddf8b5854
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443734"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="464e6-102">IMetaDataTables::GetNextGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="464e6-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="464e6-103">現在のテーブル列の次の GUID 値のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="464e6-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="464e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="464e6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="464e6-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="464e6-106">からGUID テーブルの列からのインデックス値。</span><span class="sxs-lookup"><span data-stu-id="464e6-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="464e6-107">入出力次の GUID 値のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="464e6-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="464e6-108">コメント</span><span class="sxs-lookup"><span data-stu-id="464e6-108">Remarks</span></span>  
 <span data-ttu-id="464e6-109">このメソッドは、一貫性のある結果を返さないため、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="464e6-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="464e6-110">GUID テーブルの詳細については、共通言語基盤 (CLI) のドキュメント (特に「パーティション II: メタデータの定義とセマンティクス」) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464e6-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="464e6-111">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464e6-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="464e6-112">要件</span><span class="sxs-lookup"><span data-stu-id="464e6-112">Requirements</span></span>  
 <span data-ttu-id="464e6-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="464e6-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="464e6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="464e6-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="464e6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="464e6-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="464e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464e6-117">参照</span><span class="sxs-lookup"><span data-stu-id="464e6-117">See also</span></span>

- [<span data-ttu-id="464e6-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="464e6-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="464e6-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="464e6-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
