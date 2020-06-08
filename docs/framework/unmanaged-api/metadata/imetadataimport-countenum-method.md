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
ms.openlocfilehash: 4521a3f15ec358a4d786a4533efb6b99d0e1c1cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492383"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="6fc4a-102">IMetaDataImport::CountEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="6fc4a-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="6fc4a-103">指定した列挙子によって取得された列挙体の要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="6fc4a-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc4a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6fc4a-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fc4a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fc4a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6fc4a-106">から列挙子のハンドルです。</span><span class="sxs-lookup"><span data-stu-id="6fc4a-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="6fc4a-107">入出力列挙された要素の数。</span><span class="sxs-lookup"><span data-stu-id="6fc4a-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fc4a-108">解説</span><span class="sxs-lookup"><span data-stu-id="6fc4a-108">Remarks</span></span>  
 <span data-ttu-id="6fc4a-109">によって指定されたハンドル `hEnum` は、前 `Enum` の*名前*の呼び出し (たとえば、 [IMetaDataImport:: enumtypedefs](imetadataimport-enumtypedefs-method.md)) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="6fc4a-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fc4a-110">要件</span><span class="sxs-lookup"><span data-stu-id="6fc4a-110">Requirements</span></span>  
 <span data-ttu-id="6fc4a-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fc4a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fc4a-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6fc4a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fc4a-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6fc4a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fc4a-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fc4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc4a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fc4a-115">See also</span></span>

- [<span data-ttu-id="6fc4a-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fc4a-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6fc4a-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fc4a-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
