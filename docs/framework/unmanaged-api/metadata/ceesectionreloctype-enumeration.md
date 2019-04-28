---
title: CeeSectionRelocType 列挙型
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 882242da493c49a2e6aa09888e9503dcf2933589
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906140"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="2a64a-102">CeeSectionRelocType 列挙型</span><span class="sxs-lookup"><span data-stu-id="2a64a-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="2a64a-103">種類に影響する値を提供`reloc`への呼び出しで出力される命令[iceegen::addsectionreloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a64a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a64a-104">Syntax</span></span>  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a><span data-ttu-id="2a64a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2a64a-105">Members</span></span>  
  
|<span data-ttu-id="2a64a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2a64a-106">Member</span></span>|<span data-ttu-id="2a64a-107">説明</span><span class="sxs-lookup"><span data-stu-id="2a64a-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="2a64a-108">生成のみセクション-相対的な`reloc`.reloc セクションに何も送信します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="2a64a-109">生成、`reloc`のポインター-サイズの場所。</span><span class="sxs-lookup"><span data-stu-id="2a64a-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="2a64a-110">これは、プラットフォームによって BASED_HIGHLOW または BASED_DIR64 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2a64a-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="2a64a-111">生成、`reloc`上部、下部にある 16 ビットが .reloc テーブルでは、次の単語に含まれる、32 ビットの番号の 16 ビットの。</span><span class="sxs-lookup"><span data-stu-id="2a64a-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="2a64a-112">.Reloc セクションに何も返さないトークン マップ再配置を生成します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="2a64a-113">値が相対アドレスのフィックス アップであることを示します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="2a64a-114">生成のみセクション-相対的な`reloc`.reloc セクションに何も送信します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="2a64a-115">これは、`reloc`セクションの仮想アドレスではなく、セクションのファイルの位置に対する相対パスです。</span><span class="sxs-lookup"><span data-stu-id="2a64a-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="2a64a-116">フィックス アップをコードの相対アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="2a64a-117">生成、 `reloc` ia64 に 64 ビット アドレス`movl`命令。</span><span class="sxs-lookup"><span data-stu-id="2a64a-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="2a64a-118">生成、 `reloc` 64 ビットのアドレス。</span><span class="sxs-lookup"><span data-stu-id="2a64a-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="2a64a-119">生成、 `reloc` ia64 で 25 ビット PC の相対アドレスの`br.call`命令。</span><span class="sxs-lookup"><span data-stu-id="2a64a-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="2a64a-120">生成、 `reloc` ia64 に 64 ビット PC の相対アドレスの`brl.call`命令。</span><span class="sxs-lookup"><span data-stu-id="2a64a-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="2a64a-121">30 ビット セクションの相対パスが生成されます`reloc`のタグが付けられたポインター値に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a64a-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="2a64a-122">この列挙型への追加機能を確保しやすく、sentinel 値は、内部に反映`reloc`名の配列。</span><span class="sxs-lookup"><span data-stu-id="2a64a-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="2a64a-123">基本を出力しないように指定`reloc`します。</span><span class="sxs-lookup"><span data-stu-id="2a64a-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="2a64a-124">メモリの事前修正内容のセクションではなく、ポインターを示す値のオフセット。</span><span class="sxs-lookup"><span data-stu-id="2a64a-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a64a-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a64a-125">Requirements</span></span>  
 <span data-ttu-id="2a64a-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a64a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a64a-127">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a64a-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a64a-128">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2a64a-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a64a-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a64a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a64a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a64a-130">See also</span></span>

- [<span data-ttu-id="2a64a-131">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="2a64a-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="2a64a-132">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a64a-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="2a64a-133">AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="2a64a-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
