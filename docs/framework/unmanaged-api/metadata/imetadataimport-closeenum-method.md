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
ms.openlocfilehash: 4347a4da3e58a20c98e217de3a71c448e244eb29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440122"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="bea81-102">IMetaDataImport::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="bea81-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="bea81-103">指定したハンドルによって識別される列挙子を閉じます。</span><span class="sxs-lookup"><span data-stu-id="bea81-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea81-104">構文</span><span class="sxs-lookup"><span data-stu-id="bea81-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bea81-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bea81-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="bea81-106">から閉じる列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="bea81-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bea81-107">コメント</span><span class="sxs-lookup"><span data-stu-id="bea81-107">Remarks</span></span>  
 <span data-ttu-id="bea81-108">`hEnum` によって指定されたハンドルは、前の `Enum`*名*の呼び出し (たとえば、 [IMetaDataImport:: enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="bea81-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bea81-109">要件</span><span class="sxs-lookup"><span data-stu-id="bea81-109">Requirements</span></span>  
 <span data-ttu-id="bea81-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea81-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bea81-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bea81-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="bea81-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bea81-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea81-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bea81-114">See also</span></span>

- [<span data-ttu-id="bea81-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bea81-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bea81-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bea81-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
