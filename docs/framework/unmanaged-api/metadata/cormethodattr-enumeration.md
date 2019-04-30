---
title: CorMethodAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 249de91483117db6b497fa8eae6f97c3eb0a0587
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045527"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="7eaa9-102">CorMethodAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="7eaa9-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="7eaa9-103">メソッドの機能を記述する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eaa9-104">構文</span><span class="sxs-lookup"><span data-stu-id="7eaa9-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="7eaa9-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7eaa9-105">Members</span></span>  
  
|<span data-ttu-id="7eaa9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7eaa9-106">Member</span></span>|<span data-ttu-id="7eaa9-107">説明</span><span class="sxs-lookup"><span data-stu-id="7eaa9-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="7eaa9-108">メンバーへのアクセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="7eaa9-109">メンバーを参照できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="7eaa9-110">メンバーが親の型からのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="7eaa9-111">メンバーがこのアセンブリでのみサブタイプ アクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="7eaa9-112">メンバーがアクセスできます。 アセンブリ内のすべてのユーザーがあることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="7eaa9-113">メンバーが型とサブタイプによってのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="7eaa9-114">メンバーがアクセスできるは、そのアセンブリ内の他の型と派生クラスであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="7eaa9-115">メンバーがスコープにアクセスできるアクセス権を持つすべての種類であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="7eaa9-116">インスタンスのメンバーではなく、型の一部として、メンバーが定義されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="7eaa9-117">メソッドをオーバーライドできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="7eaa9-118">メソッドをオーバーライドできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="7eaa9-119">メソッドには、名前だけではなく、名前とシグネチャで非表示にするを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="7eaa9-120">仮想テーブルのレイアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="7eaa9-121">仮想テーブルでは、このメソッドの使用、スロットが再利用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="7eaa9-122">既定値です。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="7eaa9-123">メソッドは、仮想テーブルの新しいスロットを常に取得を指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="7eaa9-124">表示は同じ型でメソッドをオーバーライドできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="7eaa9-125">メソッドが実装されていないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="7eaa9-126">メソッドが、特別なと、その名前を記述しているを指定する方法。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="7eaa9-127">メソッドの実装が PInvoke を使用して転送されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="7eaa9-128">メソッドがアンマネージ コードにエクスポートする管理対象のメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="7eaa9-129">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="7eaa9-130">共通言語ランタイムがメソッド名のエンコードを確認する必要がありますように指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="7eaa9-131">メソッドに関連付けられているセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="7eaa9-132">メソッドがセキュリティ コードを含む他のメソッドを呼び出すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7eaa9-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="7eaa9-133">Requirements</span></span>  
 <span data-ttu-id="7eaa9-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eaa9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eaa9-135">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7eaa9-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7eaa9-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eaa9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eaa9-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eaa9-137">See also</span></span>

- [<span data-ttu-id="7eaa9-138">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="7eaa9-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
