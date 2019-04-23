---
title: IMetaDataTables::GetTableIndex メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eebef02babdca5305deaa4ae11e4bca3bf8bf504
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154402"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="d59f2-102">IMetaDataTables::GetTableIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="d59f2-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="d59f2-103">指定したトークンによって参照されるテーブルのインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d59f2-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d59f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="d59f2-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d59f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d59f2-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="d59f2-106">[in]テーブルを参照するトークンです。</span><span class="sxs-lookup"><span data-stu-id="d59f2-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="d59f2-107">[out]返される参照先のテーブルのインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d59f2-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d59f2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d59f2-108">Remarks</span></span>  
 <span data-ttu-id="d59f2-109">お勧めしません、このメソッドを使用して一貫性のある結果を返さないためです。</span><span class="sxs-lookup"><span data-stu-id="d59f2-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="d59f2-110">GUID の表については、ドキュメントを参照して、共通言語基盤 (CLI)、特に"第 2 部。メタデータの定義およびセマンティクス"。</span><span class="sxs-lookup"><span data-stu-id="d59f2-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="d59f2-111">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d59f2-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d59f2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d59f2-112">Requirements</span></span>  
 <span data-ttu-id="d59f2-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d59f2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d59f2-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d59f2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d59f2-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d59f2-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d59f2-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d59f2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59f2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d59f2-117">See also</span></span>

- [<span data-ttu-id="d59f2-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d59f2-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d59f2-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d59f2-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
