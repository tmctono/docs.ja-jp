---
title: CorTypeAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f65c2f74ec5efda027d90b3ffda9a5da5c239122
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025718"
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="17e6c-102">CorTypeAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="17e6c-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="17e6c-103">メタデータ型を示す値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="17e6c-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="17e6c-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="17e6c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="17e6c-105">Members</span></span>  
  
|<span data-ttu-id="17e6c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="17e6c-106">Member</span></span>|<span data-ttu-id="17e6c-107">説明</span><span class="sxs-lookup"><span data-stu-id="17e6c-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="17e6c-108">可視性の種類の情報に使用されます。</span><span class="sxs-lookup"><span data-stu-id="17e6c-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="17e6c-109">型がパブリック スコープでないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="17e6c-110">パブリック スコープで型を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="17e6c-111">型がパブリックな可視性と入れ子になったことを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="17e6c-112">型がプライベートの可視性を持つ入れ子になったことを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="17e6c-113">ファミリの可視性を持つ型が入れ子になっていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="17e6c-114">アセンブリの可視性を持つ型が入れ子になっていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="17e6c-115">ファミリとアセンブリの可視性を持つ型が入れ子になっていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="17e6c-116">ファミリまたはアセンブリの可視性を持つ型が入れ子になっていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="17e6c-117">型のレイアウト情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="17e6c-118">この型のフィールドが自動的にレイアウトされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="17e6c-119">この型のフィールドが順番にレイアウトされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="17e6c-120">フィールド レイアウトは明示的に指定されたを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="17e6c-121">型に関するセマンティック情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="17e6c-122">型がクラスであることを示します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="17e6c-123">型がインターフェイスであることを示します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="17e6c-124">型が抽象的であることを示します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="17e6c-125">型を拡張できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="17e6c-126">特殊なクラス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-126">Specifies that the class name is special.</span></span> <span data-ttu-id="17e6c-127">その名前で記述する方法。</span><span class="sxs-lookup"><span data-stu-id="17e6c-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="17e6c-128">型がインポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="17e6c-129">型がシリアル化可能なことを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="17e6c-130">この型が、Windows ランタイム型であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-130">Specifies that this type is a Windows Runtime type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="17e6c-131">文字列のエンコードおよび書式設定方法に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="17e6c-132">この型に、LPTSTR ANSI として解釈するを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="17e6c-133">この型が Unicode として LPTSTR を解釈するを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="17e6c-134">この型が自動的に LPTSTR を解釈することを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="17e6c-135">型が非標準のエンコーディングを持つことを指定で指定された`CustomFormatMask`します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="17e6c-136">このマスクを使用して、ネイティブ相互運用機能の非標準のエンコード情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="17e6c-137">これら 2 つのビットの値の意味では、指定されていません。</span><span class="sxs-lookup"><span data-stu-id="17e6c-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="17e6c-138">静的フィールドにアクセスする最初の試行する前に、型を初期化する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="17e6c-139">型がエクスポートされたことを指定します。 型フォワーダーとします。</span><span class="sxs-lookup"><span data-stu-id="17e6c-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="17e6c-140">このフラグは、次のフラグは、共通言語ランタイムによって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="17e6c-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="17e6c-141">名前のエンコーディングに共通言語ランタイムが確認する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="17e6c-142">型が関連付けられているセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e6c-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17e6c-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="17e6c-143">Requirements</span></span>  
 <span data-ttu-id="17e6c-144">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e6c-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17e6c-145">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="17e6c-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="17e6c-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17e6c-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e6c-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="17e6c-147">See also</span></span>

- [<span data-ttu-id="17e6c-148">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="17e6c-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
