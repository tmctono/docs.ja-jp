---
title: CorElementType Enumeration1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d47e250a35640d15bd494d99442271a070a1dd0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781903"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="ae678-102">CorElementType Enumeration1</span><span class="sxs-lookup"><span data-stu-id="ae678-102">CorElementType Enumeration1</span></span>

<span data-ttu-id="ae678-103">共通言語ランタイムを指定します<xref:System.Type>、型修飾子、またはメタデータの型シグネチャの種類に関する情報。</span><span class="sxs-lookup"><span data-stu-id="ae678-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae678-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae678-104">Syntax</span></span>

```cpp
typedef enum CorElementType {
    ELEMENT_TYPE_END            = 0x0,
    ELEMENT_TYPE_VOID           = 0x1,
    ELEMENT_TYPE_BOOLEAN        = 0x2,
    ELEMENT_TYPE_CHAR           = 0x3,
    ELEMENT_TYPE_I1             = 0x4,
    ELEMENT_TYPE_U1             = 0x5,
    ELEMENT_TYPE_I2             = 0x6,
    ELEMENT_TYPE_U2             = 0x7,
    ELEMENT_TYPE_I4             = 0x8,
    ELEMENT_TYPE_U4             = 0x9,
    ELEMENT_TYPE_I8             = 0xa,
    ELEMENT_TYPE_U8             = 0xb,
    ELEMENT_TYPE_R4             = 0xc,
    ELEMENT_TYPE_R8             = 0xd,
    ELEMENT_TYPE_STRING         = 0xe,

    ELEMENT_TYPE_PTR            = 0xf,
    ELEMENT_TYPE_BYREF          = 0x10,

    ELEMENT_TYPE_VALUETYPE      = 0x11,
    ELEMENT_TYPE_CLASS          = 0x12,
    ELEMENT_TYPE_VAR            = 0x13,
    ELEMENT_TYPE_ARRAY          = 0x14,
    ELEMENT_TYPE_GENERICINST    = 0x15,
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,

    ELEMENT_TYPE_I              = 0x18,
    ELEMENT_TYPE_U              = 0x19,
    ELEMENT_TYPE_FNPTR          = 0x1B,
    ELEMENT_TYPE_OBJECT         = 0x1C,
    ELEMENT_TYPE_SZARRAY        = 0x1D,
    ELEMENT_TYPE_MVAR           = 0x1e,

    ELEMENT_TYPE_CMOD_REQD      = 0x1F,
    ELEMENT_TYPE_CMOD_OPT       = 0x20,

    ELEMENT_TYPE_INTERNAL       = 0x21,
    ELEMENT_TYPE_MAX            = 0x22,

    ELEMENT_TYPE_MODIFIER       = 0x40,
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER

} CorElementType;
```

## <a name="members"></a><span data-ttu-id="ae678-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ae678-105">Members</span></span>

|<span data-ttu-id="ae678-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ae678-106">Member</span></span>|<span data-ttu-id="ae678-107">説明</span><span class="sxs-lookup"><span data-stu-id="ae678-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="ae678-108">内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="ae678-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="ae678-109">Void 型。</span><span class="sxs-lookup"><span data-stu-id="ae678-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="ae678-110">ブール型</span><span class="sxs-lookup"><span data-stu-id="ae678-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="ae678-111">文字型。</span><span class="sxs-lookup"><span data-stu-id="ae678-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="ae678-112">1 バイトの符号付き整数では。</span><span class="sxs-lookup"><span data-stu-id="ae678-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="ae678-113">1 バイトの符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="ae678-114">符号付きの 2 バイト整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="ae678-115">2 バイトの符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="ae678-116">符号付きの 4 バイト整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="ae678-117">4 バイトの符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="ae678-118">符号付き 8 バイト整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="ae678-119">8 バイトの符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="ae678-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="ae678-120">4 バイト浮動小数点。</span><span class="sxs-lookup"><span data-stu-id="ae678-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="ae678-121">8 バイト浮動小数点。</span><span class="sxs-lookup"><span data-stu-id="ae678-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="ae678-122">System.String 型。</span><span class="sxs-lookup"><span data-stu-id="ae678-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="ae678-123">ポインター型の修飾子。</span><span class="sxs-lookup"><span data-stu-id="ae678-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="ae678-124">参照型の修飾子。</span><span class="sxs-lookup"><span data-stu-id="ae678-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="ae678-125">値の型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="ae678-126">クラス型の修飾子。</span><span class="sxs-lookup"><span data-stu-id="ae678-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="ae678-127">クラスの変数の型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="ae678-128">多次元配列の型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="ae678-129">ジェネリック型の型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="ae678-130">型指定された参照。</span><span class="sxs-lookup"><span data-stu-id="ae678-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="ae678-131">ネイティブの整数のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ae678-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="ae678-132">符号なしネイティブ整数のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ae678-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="ae678-133">関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ae678-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="ae678-134">System.Object 型。</span><span class="sxs-lookup"><span data-stu-id="ae678-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="ae678-135">1 次元、0 の配列の下限の型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="ae678-136">メソッドの変数の型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="ae678-137">C 言語には、修飾子が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae678-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="ae678-138">C 言語の省略可能な修飾子。</span><span class="sxs-lookup"><span data-stu-id="ae678-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="ae678-139">内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="ae678-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="ae678-140">無効な型。</span><span class="sxs-lookup"><span data-stu-id="ae678-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="ae678-141">内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="ae678-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="ae678-142">Sentinel 可変個のパラメーターの一覧については、型修飾子です。</span><span class="sxs-lookup"><span data-stu-id="ae678-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="ae678-143">内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="ae678-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ae678-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae678-144">Remarks</span></span>

<span data-ttu-id="ae678-145">型修飾子より複雑な型を表すための基礎を形成します。</span><span class="sxs-lookup"><span data-stu-id="ae678-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="ae678-146">A`CorElementType`型修飾子の値が値型シグネチャ内直後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae678-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="ae678-147">次の値、`CorElementType`型修飾子の値を指定できます、`CorElementType`単純型の値、メタデータ トークン、または次の表で指定されているその他の値。</span><span class="sxs-lookup"><span data-stu-id="ae678-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="ae678-148">すべての数値 (*数*、*引数カウント*、*メタデータ トークン*、*ランク*、*カウント*、および*バインド*) 圧縮された整数として格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae678-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="ae678-149">参照してください[標準 ECMA 335 の共通言語基盤 (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487)詳細については、ECMA の Web サイト。</span><span class="sxs-lookup"><span data-stu-id="ae678-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="ae678-150">型修飾子</span><span class="sxs-lookup"><span data-stu-id="ae678-150">Type modifier</span></span>|<span data-ttu-id="ae678-151">Format</span><span class="sxs-lookup"><span data-stu-id="ae678-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="ae678-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="ae678-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="ae678-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="ae678-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="ae678-154">ELEMENT_TYPE_VALUETYPE \<、`mdTypeDef`メタデータ トークン ></span><span class="sxs-lookup"><span data-stu-id="ae678-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="ae678-155">ELEMENT_TYPE_CLASS \<、`mdTypeDef`メタデータ トークン ></span><span class="sxs-lookup"><span data-stu-id="ae678-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="ae678-156">ELEMENT_TYPE_VAR \<number></span><span class="sxs-lookup"><span data-stu-id="ae678-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="ae678-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span><span class="sxs-lookup"><span data-stu-id="ae678-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="ae678-158">ELEMENT_TYPE_GENERICINST \<、`mdTypeDef`メタデータ トークン >\<引数カウント > \<arg1 >.\<argN ></span><span class="sxs-lookup"><span data-stu-id="ae678-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="ae678-159">Typ ELEMENT_TYPE_FNPTR\<には関数の呼び出し規約を含む完全なシグネチャ ></span><span class="sxs-lookup"><span data-stu-id="ae678-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="ae678-160">ELEMENT_TYPE_SZARRAY \<、`CorElementType`値 ></span><span class="sxs-lookup"><span data-stu-id="ae678-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="ae678-161">ELEMENT_TYPE_MVAR \<number></span><span class="sxs-lookup"><span data-stu-id="ae678-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="ae678-162">ELEMENT_TYPE_\<、`mdTypeRef`または`mdTypeDef`メタデータ トークン ></span><span class="sxs-lookup"><span data-stu-id="ae678-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="ae678-163">E_T_CMOD_OPT \<、`mdTypeRef`または`mdTypeDef`メタデータ トークン ></span><span class="sxs-lookup"><span data-stu-id="ae678-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="ae678-164">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae678-164">Requirements</span></span>

<span data-ttu-id="ae678-165">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae678-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ae678-166">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ae678-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="ae678-167">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae678-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ae678-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae678-168">See also</span></span>

- [<span data-ttu-id="ae678-169">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="ae678-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
