---
title: IMetaDataImport::CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f27955467436d562c6a9acc9d7f666427e4c85b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770716"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="e69ce-102">IMetaDataImport::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="e69ce-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="e69ce-103">指定したハンドルによって識別される列挙子を閉じます。</span><span class="sxs-lookup"><span data-stu-id="e69ce-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e69ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="e69ce-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e69ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e69ce-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e69ce-106">[in]閉じる、列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="e69ce-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e69ce-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e69ce-107">Remarks</span></span>  
 <span data-ttu-id="e69ce-108">指定されたハンドル`hEnum`以前から取得されます`Enum`*名前*呼び出し (たとえば、 [imetadataimport::enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="e69ce-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e69ce-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e69ce-109">Requirements</span></span>  
 <span data-ttu-id="e69ce-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e69ce-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e69ce-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e69ce-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e69ce-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e69ce-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e69ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69ce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e69ce-114">See also</span></span>

- [<span data-ttu-id="e69ce-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e69ce-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e69ce-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e69ce-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
