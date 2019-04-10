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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aa9b84c9e16811f799a3cd2ad096508db3f7d34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220501"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="9ae62-102">CorGenericParamAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="9ae62-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="9ae62-103">記述する値が含まれています、<xref:System.Type>の呼び出しで使用される、ジェネリック型パラメーター [imetadataemit 2::definegenericparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ae62-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae62-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ae62-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="9ae62-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9ae62-105">Members</span></span>  
  
|<span data-ttu-id="9ae62-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9ae62-106">Member</span></span>|<span data-ttu-id="9ae62-107">説明</span><span class="sxs-lookup"><span data-stu-id="9ae62-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="9ae62-108">パラメーターの分散は、インターフェイスおよびデリゲートのジェネリック パラメーターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ae62-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="9ae62-109">差異がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="9ae62-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="9ae62-110">共変性を示します。</span><span class="sxs-lookup"><span data-stu-id="9ae62-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="9ae62-111">反変性を示します。</span><span class="sxs-lookup"><span data-stu-id="9ae62-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="9ae62-112">特殊な制約は、いずれかに適用できる<xref:System.Type>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9ae62-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="9ae62-113">制約が適用されないことを示します、<xref:System.Type>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9ae62-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="9ae62-114">示します、<xref:System.Type>パラメーターは参照型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae62-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="9ae62-115">示します、<xref:System.Type>パラメーターは null 値にすることはできません、値の型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae62-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="9ae62-116">示します、<xref:System.Type>パラメーターの既定のコンス トラクター パラメーターをとらない必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae62-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ae62-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ae62-117">Requirements</span></span>  
 <span data-ttu-id="9ae62-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae62-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae62-119">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9ae62-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="9ae62-120">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9ae62-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9ae62-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ae62-121">See also</span></span>

- [<span data-ttu-id="9ae62-122">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="9ae62-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
