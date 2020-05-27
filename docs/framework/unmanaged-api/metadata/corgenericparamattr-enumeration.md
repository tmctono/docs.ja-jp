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
ms.openlocfilehash: ea84b742c901ba58a3bb730f1f5033a0d90610ce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007378"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="9c7e5-102">CorGenericParamAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="9c7e5-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="9c7e5-103"><xref:System.Type> [IMetaDataEmit2::D efineGenericParam](imetadataemit2-definegenericparam-method.md)の呼び出しで使用される、ジェネリック型のパラメーターを記述する値を格納します。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7e5-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c7e5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9c7e5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9c7e5-105">Members</span></span>  
  
|<span data-ttu-id="9c7e5-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9c7e5-106">Member</span></span>|<span data-ttu-id="9c7e5-107">説明</span><span class="sxs-lookup"><span data-stu-id="9c7e5-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="9c7e5-108">パラメーターの分散は、インターフェイスとデリゲートのジェネリックパラメーターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="9c7e5-109">分散が存在しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="9c7e5-110">共変性を示します。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="9c7e5-111">反変性を示します。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="9c7e5-112">特殊な制約は、任意のパラメーターに適用でき <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="9c7e5-113">パラメーターに制約が適用されないことを示し <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="9c7e5-114">パラメーターが参照型である必要があることを示し <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="9c7e5-115"><xref:System.Type>パラメーターが null 値にできない値型である必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="9c7e5-116">パラメーターを受け取らない既定のパブリックコンストラクターがパラメーターに必要であることを示し <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c7e5-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c7e5-117">Requirements</span></span>  
 <span data-ttu-id="9c7e5-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c7e5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c7e5-119">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="9c7e5-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9c7e5-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7e5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7e5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c7e5-121">See also</span></span>

- [<span data-ttu-id="9c7e5-122">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="9c7e5-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
