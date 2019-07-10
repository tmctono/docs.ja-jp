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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1075643bbd17765bf33a26038fc6beaf32d0aebb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781498"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="cac02-102">IMetaDataTables::GetGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="cac02-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="cac02-103">指定したインデックス位置の行から GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="cac02-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac02-104">構文</span><span class="sxs-lookup"><span data-stu-id="cac02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cac02-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cac02-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="cac02-106">[in]GUID の取得元の行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="cac02-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="cac02-107">[out]GUID へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cac02-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cac02-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="cac02-108">Remarks</span></span>  
 <span data-ttu-id="cac02-109">お勧めしません、このメソッドを使用して一貫性のある結果を返さないためです。</span><span class="sxs-lookup"><span data-stu-id="cac02-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="cac02-110">GUID の表については、ドキュメントを参照して、共通言語基盤 (CLI)、特に"第 2 部。メタデータの定義およびセマンティクス"。</span><span class="sxs-lookup"><span data-stu-id="cac02-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="cac02-111">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac02-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cac02-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cac02-112">Requirements</span></span>  
 <span data-ttu-id="cac02-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cac02-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cac02-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cac02-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="cac02-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cac02-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cac02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac02-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cac02-117">See also</span></span>

- [<span data-ttu-id="cac02-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cac02-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cac02-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cac02-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
