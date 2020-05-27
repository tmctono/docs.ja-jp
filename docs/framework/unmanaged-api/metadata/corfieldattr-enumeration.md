---
title: CorFieldAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: dea69e18fc517eddddc5b99950a6f3b16ee3e426
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007404"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="4f661-102">CorFieldAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="4f661-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="4f661-103">フィールドについてのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f661-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f661-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f661-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="4f661-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4f661-105">Members</span></span>  
  
|<span data-ttu-id="4f661-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4f661-106">Member</span></span>|<span data-ttu-id="4f661-107">説明</span><span class="sxs-lookup"><span data-stu-id="4f661-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="4f661-108">アクセシビリティ情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="4f661-109">フィールドを参照できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="4f661-110">フィールドがその親の型によってのみアクセス可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="4f661-111">アセンブリ内の派生クラスによってフィールドにアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="4f661-112">アセンブリ内のすべての型からフィールドにアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="4f661-113">フィールドがその型および派生クラスによってのみアクセス可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="4f661-114">派生クラスおよびそのアセンブリ内のすべての型によってフィールドにアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="4f661-115">このスコープの可視性を持つすべての型からフィールドにアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="4f661-116">フィールドがインスタンスメンバーではなく、その型のメンバーであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="4f661-117">初期化後にフィールドを変更できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="4f661-118">フィールド値がコンパイル時の定数であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="4f661-119">型がリモート処理されるときに、フィールドをシリアル化しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="4f661-120">フィールドが特別であること、およびその名前で方法が説明されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="4f661-121">フィールドの実装が PInvoke 経由で転送されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="4f661-122">共通言語ランタイムによる内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="4f661-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="4f661-123">共通言語ランタイムメタデータの内部 Api が名前のエンコーディングを確認する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="4f661-124">フィールドにマーシャリング情報が含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="4f661-125">フィールドが既定値を持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="4f661-126">フィールドが相対仮想アドレスを持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f661-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f661-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f661-127">Requirements</span></span>  
 <span data-ttu-id="4f661-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f661-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f661-129">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="4f661-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4f661-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f661-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f661-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f661-131">See also</span></span>

- [<span data-ttu-id="4f661-132">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="4f661-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
