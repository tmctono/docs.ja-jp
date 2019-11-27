---
title: CorGenericParamAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: e4abf876681d5b04555c9f030a94b722874e326e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450285"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="04c2c-102">CorGenericParamAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="04c2c-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="04c2c-103">[IMetaDataEmit2::D efineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)の呼び出しで使用される、ジェネリック型の <xref:System.Type> パラメーターを記述する値を格納します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c2c-104">構文</span><span class="sxs-lookup"><span data-stu-id="04c2c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="04c2c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="04c2c-105">Members</span></span>  
  
|<span data-ttu-id="04c2c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="04c2c-106">Member</span></span>|<span data-ttu-id="04c2c-107">説明</span><span class="sxs-lookup"><span data-stu-id="04c2c-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="04c2c-108">パラメーターの分散は、インターフェイスとデリゲートのジェネリックパラメーターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04c2c-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="04c2c-109">分散が存在しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="04c2c-110">共変性を示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="04c2c-111">反変性を示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="04c2c-112">特殊な制約は、任意の <xref:System.Type> パラメーターに適用できます。</span><span class="sxs-lookup"><span data-stu-id="04c2c-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="04c2c-113"><xref:System.Type> パラメーターに制約が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="04c2c-114"><xref:System.Type> パラメーターが参照型である必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="04c2c-115"><xref:System.Type> パラメーターを null 値にすることができない値型である必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="04c2c-116"><xref:System.Type> パラメーターに、パラメーターをとらない既定のパブリックコンストラクターが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="04c2c-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04c2c-117">要件</span><span class="sxs-lookup"><span data-stu-id="04c2c-117">Requirements</span></span>  
 <span data-ttu-id="04c2c-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04c2c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c2c-119">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="04c2c-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="04c2c-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c2c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c2c-121">参照</span><span class="sxs-lookup"><span data-stu-id="04c2c-121">See also</span></span>

- [<span data-ttu-id="04c2c-122">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="04c2c-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
