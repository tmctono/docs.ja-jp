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
ms.openlocfilehash: d3e056bc93c2faf2b1509536b8d8d4df6886dd20
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937377"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="cb0ce-102">IMetaDataTables::GetTableIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="cb0ce-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="cb0ce-103">指定したトークンによって参照されるテーブルのインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb0ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb0ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb0ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb0ce-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="cb0ce-106">からテーブルを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="cb0ce-107">入出力参照されるテーブルの、返されたインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb0ce-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb0ce-108">Remarks</span></span>  
 <span data-ttu-id="cb0ce-109">このメソッドは、一貫性のある結果を返さないため、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="cb0ce-110">GUID テーブルの詳細については、共通言語基盤 (CLI) のドキュメント (特に「パーティション II: メタデータの定義とセマンティクス」) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="cb0ce-111">ドキュメントはオンラインで入手できます。「 [ecma C#および共通言語基盤の標準](../../../standard/components.md#applicable-standards)と[標準 ECMA-335-共通言語基盤 (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb0ce-112">要件</span><span class="sxs-lookup"><span data-stu-id="cb0ce-112">Requirements</span></span>  
 <span data-ttu-id="cb0ce-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb0ce-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="cb0ce-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb0ce-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb0ce-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb0ce-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb0ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0ce-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb0ce-117">See also</span></span>

- [<span data-ttu-id="cb0ce-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb0ce-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cb0ce-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb0ce-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
