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
ms.openlocfilehash: 2ac29de437e746f1524fc1427c47eb8f5c761be7
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937807"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="4b043-102">IMetaDataTables::GetGuid メソッド</span><span class="sxs-lookup"><span data-stu-id="4b043-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="4b043-103">指定したインデックス位置にある行から GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="4b043-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b043-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b043-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b043-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b043-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="4b043-106">からGUID の取得元となる行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="4b043-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="4b043-107">入出力GUID へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4b043-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b043-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b043-108">Remarks</span></span>  

  <span data-ttu-id="4b043-109">このメソッドは、一貫性のある結果を返さないため、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b043-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="4b043-110">GUID テーブルの詳細については、共通言語基盤 (CLI) のドキュメント (特に「パーティション II: メタデータの定義とセマンティクス」) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b043-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="4b043-111">ドキュメントはオンラインで入手できます。「 [ecma C#および共通言語基盤の標準](../../../standard/components.md#applicable-standards)と[標準 ECMA-335-共通言語基盤 (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b043-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b043-112">要件</span><span class="sxs-lookup"><span data-stu-id="4b043-112">Requirements</span></span>  
 <span data-ttu-id="4b043-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b043-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b043-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4b043-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b043-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b043-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b043-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b043-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b043-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b043-117">See also</span></span>

- [<span data-ttu-id="4b043-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b043-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="4b043-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b043-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
