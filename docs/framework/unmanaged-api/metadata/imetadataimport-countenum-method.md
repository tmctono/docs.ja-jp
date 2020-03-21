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
ms.openlocfilehash: b780ca513d8a0b4f88e66594e86e9ff8290f6523
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177354"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="54166-102">IMetaDataImport::CountEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="54166-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="54166-103">指定した列挙子によって取得された列挙体内の要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="54166-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54166-104">構文</span><span class="sxs-lookup"><span data-stu-id="54166-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54166-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54166-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="54166-106">[in]列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="54166-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="54166-107">[アウト]列挙された要素の数。</span><span class="sxs-lookup"><span data-stu-id="54166-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54166-108">解説</span><span class="sxs-lookup"><span data-stu-id="54166-108">Remarks</span></span>  
 <span data-ttu-id="54166-109">指定された`hEnum`ハンドルは、以前`Enum`の*名前*の呼び出しから取得されます (たとえば[、IMetaDataImport::EnumTypeDefs)。](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)</span><span class="sxs-lookup"><span data-stu-id="54166-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54166-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="54166-110">Requirements</span></span>  
 <span data-ttu-id="54166-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54166-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54166-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="54166-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54166-113">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="54166-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54166-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54166-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54166-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="54166-115">See also</span></span>

- [<span data-ttu-id="54166-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54166-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="54166-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54166-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
