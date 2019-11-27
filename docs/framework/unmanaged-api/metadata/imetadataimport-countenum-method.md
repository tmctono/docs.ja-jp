---
title: IMetaDataImport::CountEnum メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: 0c78ce8192d6456dd1b1be990d87b9209b028e09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440360"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="8993e-102">IMetaDataImport::CountEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="8993e-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="8993e-103">指定した列挙子によって取得された列挙体の要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="8993e-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8993e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8993e-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8993e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8993e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8993e-106">から列挙子のハンドルです。</span><span class="sxs-lookup"><span data-stu-id="8993e-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="8993e-107">入出力列挙された要素の数。</span><span class="sxs-lookup"><span data-stu-id="8993e-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8993e-108">コメント</span><span class="sxs-lookup"><span data-stu-id="8993e-108">Remarks</span></span>  
 <span data-ttu-id="8993e-109">`hEnum` によって指定されたハンドルは、前の `Enum`*名*の呼び出し (たとえば、 [IMetaDataImport:: enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="8993e-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8993e-110">要件</span><span class="sxs-lookup"><span data-stu-id="8993e-110">Requirements</span></span>  
 <span data-ttu-id="8993e-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8993e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8993e-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8993e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8993e-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8993e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8993e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8993e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8993e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8993e-115">See also</span></span>

- [<span data-ttu-id="8993e-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8993e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8993e-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8993e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
