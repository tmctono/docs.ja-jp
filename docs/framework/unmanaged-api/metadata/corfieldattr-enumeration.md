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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 432e202eb8db105e8d56d3d36cdc8001bac5320c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182378"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="75501-102">CorFieldAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="75501-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="75501-103">フィールドについてのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="75501-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75501-104">構文</span><span class="sxs-lookup"><span data-stu-id="75501-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="75501-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="75501-105">Members</span></span>  
  
|<span data-ttu-id="75501-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="75501-106">Member</span></span>|<span data-ttu-id="75501-107">説明</span><span class="sxs-lookup"><span data-stu-id="75501-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="75501-108">アクセシビリティに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="75501-109">フィールドを参照できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="75501-110">フィールドが親の型からのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="75501-111">フィールドにそのアセンブリの派生クラスからアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="75501-112">フィールドにそのアセンブリ内のすべての型からアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="75501-113">フィールドの型によってのみアクセスできますが、派生クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="75501-114">フィールドにそのアセンブリ内のすべての型と派生クラスによってアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="75501-115">フィールドがこのスコープの可視性を持つすべての種類でアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="75501-116">フィールドがインスタンス メンバーではなく、その型のメンバーであるを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="75501-117">初期化された後に、フィールドを変更できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="75501-118">フィールド値がコンパイル時定数であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="75501-119">その型は、リモート処理は実行時にフィールドはシリアルされないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="75501-120">フィールドに、特別なことと、その名前を記述しているを指定しますか。</span><span class="sxs-lookup"><span data-stu-id="75501-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="75501-121">フィールドの実装が PInvoke 経由で転送されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="75501-122">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="75501-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="75501-123">共通言語ランタイム メタデータの内部 Api が名前のエンコーディングを確認する必要がありますように指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="75501-124">フィールドにマーシャ リング情報が含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="75501-125">フィールドが既定値を持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="75501-126">フィールドの相対仮想アドレスを持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="75501-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75501-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="75501-127">Requirements</span></span>  
 <span data-ttu-id="75501-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75501-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75501-129">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="75501-129">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="75501-130">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="75501-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75501-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="75501-131">See also</span></span>

- [<span data-ttu-id="75501-132">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="75501-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
