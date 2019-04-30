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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b23e1d26d62012efe338eeb179db0e7ee17cd658
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042368"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="6ba0c-102">IMetaDataTables::GetNextGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="6ba0c-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="6ba0c-103">現在のテーブルの列には、次の GUID 値のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ba0c-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ba0c-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ba0c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ba0c-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="6ba0c-106">[in]GUID のテーブル列からインデックス値。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="6ba0c-107">[out]次の GUID 値のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ba0c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ba0c-108">Remarks</span></span>  
 <span data-ttu-id="6ba0c-109">お勧めしません、このメソッドを使用して一貫性のある結果を返さないためです。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="6ba0c-110">GUID の表については、ドキュメントを参照して、共通言語基盤 (CLI)、特に"第 2 部。メタデータの定義およびセマンティクス"。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="6ba0c-111">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ba0c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ba0c-112">Requirements</span></span>  
 <span data-ttu-id="6ba0c-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba0c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ba0c-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6ba0c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ba0c-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6ba0c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ba0c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ba0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba0c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ba0c-117">See also</span></span>

- [<span data-ttu-id="6ba0c-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ba0c-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6ba0c-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ba0c-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
