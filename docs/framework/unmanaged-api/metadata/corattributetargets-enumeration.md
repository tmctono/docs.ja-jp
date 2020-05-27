---
title: CorAttributeTargets 列挙型
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: f1836f26af99f91ab1765107573f6b067edd5e95
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007924"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="42e96-102">CorAttributeTargets 列挙型</span><span class="sxs-lookup"><span data-stu-id="42e96-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="42e96-103">属性を適用できるアプリケーション要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="42e96-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e96-104">構文</span><span class="sxs-lookup"><span data-stu-id="42e96-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="42e96-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="42e96-105">Members</span></span>  
  
|<span data-ttu-id="42e96-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="42e96-106">Member</span></span>|<span data-ttu-id="42e96-107">説明</span><span class="sxs-lookup"><span data-stu-id="42e96-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="42e96-108">アセンブリに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="42e96-109">属性は、移植可能な実行可能ファイル (.dll または .exe) モジュールに適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="42e96-110">クラスに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="42e96-111">構造体、つまり、値型に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="42e96-112">列挙体に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="42e96-113">コンストラクターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="42e96-114">メソッドに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="42e96-115">プロパティに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="42e96-116">フィールドに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="42e96-117">イベントに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="42e96-118">インターフェイスに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="42e96-119">パラメーターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="42e96-120">デリゲートに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="42e96-121">ジェネリック パラメーターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="42e96-122">任意のアプリケーション要素に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="42e96-123">属性は、クラスのメンバーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42e96-124">コメント</span><span class="sxs-lookup"><span data-stu-id="42e96-124">Remarks</span></span>  
 <span data-ttu-id="42e96-125">`CorAttributeTargets`列挙値をビットごとの or 演算と組み合わせて、適切な組み合わせを取得できます。</span><span class="sxs-lookup"><span data-stu-id="42e96-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="42e96-126">は、 `CorAttributeTargets` マネージ列挙に似て <xref:System.AttributeTargets?displayProperty=nameWithType> います。</span><span class="sxs-lookup"><span data-stu-id="42e96-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e96-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="42e96-127">Requirements</span></span>  
 <span data-ttu-id="42e96-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e96-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e96-129">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="42e96-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="42e96-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e96-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e96-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="42e96-131">See also</span></span>

- [<span data-ttu-id="42e96-132">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="42e96-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
