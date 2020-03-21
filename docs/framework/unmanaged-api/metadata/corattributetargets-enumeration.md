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
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176202"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="5857c-102">CorAttributeTargets 列挙型</span><span class="sxs-lookup"><span data-stu-id="5857c-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="5857c-103">属性を適用できるアプリケーション要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="5857c-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5857c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5857c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5857c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5857c-105">Members</span></span>  
  
|<span data-ttu-id="5857c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5857c-106">Member</span></span>|<span data-ttu-id="5857c-107">説明</span><span class="sxs-lookup"><span data-stu-id="5857c-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="5857c-108">アセンブリに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="5857c-109">属性は、ポータブル実行可能 (.dll または .exe) モジュールに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="5857c-110">クラスに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="5857c-111">構造体、つまり、値型に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="5857c-112">列挙体に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="5857c-113">コンストラクターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="5857c-114">メソッドに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="5857c-115">プロパティに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="5857c-116">フィールドに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="5857c-117">イベントに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="5857c-118">インターフェイスに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="5857c-119">パラメーターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="5857c-120">デリゲートに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="5857c-121">ジェネリック パラメーターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="5857c-122">任意のアプリケーション要素に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="5857c-123">属性はクラスのメンバーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5857c-124">解説</span><span class="sxs-lookup"><span data-stu-id="5857c-124">Remarks</span></span>  
 <span data-ttu-id="5857c-125">列挙`CorAttributeTargets`値をビットごとの OR 演算と組み合わせて、優先する組み合わせを取得できます。</span><span class="sxs-lookup"><span data-stu-id="5857c-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="5857c-126">マネージ`CorAttributeTargets`<xref:System.AttributeTargets?displayProperty=nameWithType>列挙体と並列処理を行います。</span><span class="sxs-lookup"><span data-stu-id="5857c-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5857c-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="5857c-127">Requirements</span></span>  
 <span data-ttu-id="5857c-128">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5857c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5857c-129">**ヘッダー:** コルドル.h</span><span class="sxs-lookup"><span data-stu-id="5857c-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5857c-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5857c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5857c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="5857c-131">See also</span></span>

- [<span data-ttu-id="5857c-132">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="5857c-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
