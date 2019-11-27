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
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444159"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="dda11-102">CeeSectionRelocType 列挙型</span><span class="sxs-lookup"><span data-stu-id="dda11-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="dda11-103">[ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)への呼び出しで生成される `reloc` 命令の型に影響を与える値を提供します。</span><span class="sxs-lookup"><span data-stu-id="dda11-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda11-104">構文</span><span class="sxs-lookup"><span data-stu-id="dda11-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="dda11-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="dda11-105">Members</span></span>  
  
|<span data-ttu-id="dda11-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="dda11-106">Member</span></span>|<span data-ttu-id="dda11-107">説明</span><span class="sxs-lookup"><span data-stu-id="dda11-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="dda11-108">では、セクション相対 `reloc`が生成され、reloc セクションには何も送信されません。</span><span class="sxs-lookup"><span data-stu-id="dda11-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="dda11-109">ポインターサイズの位置の `reloc` を生成します。</span><span class="sxs-lookup"><span data-stu-id="dda11-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="dda11-110">これは、プラットフォームに応じて BASED_HIGHLOW または BASED_DIR64 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="dda11-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="dda11-111">では、32ビット数値の上位16ビットの `reloc` が生成されます。この場合、下位16ビットが、reloc テーブルの次の単語に含まれます。</span><span class="sxs-lookup"><span data-stu-id="dda11-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="dda11-112">トークンマップの再配置を生成し、reloc セクションに何も送信しません。</span><span class="sxs-lookup"><span data-stu-id="dda11-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="dda11-113">値が相対アドレスの修正であることを示します。</span><span class="sxs-lookup"><span data-stu-id="dda11-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="dda11-114">では、セクション相対 `reloc`が生成され、reloc セクションには何も送信されません。</span><span class="sxs-lookup"><span data-stu-id="dda11-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="dda11-115">この `reloc` は、セクションの仮想アドレスではなく、セクションのファイルの位置を基準としています。</span><span class="sxs-lookup"><span data-stu-id="dda11-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="dda11-116">コード相対アドレスのフィックスアップを指定します。</span><span class="sxs-lookup"><span data-stu-id="dda11-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="dda11-117">Ia64 `movl` 命令に64ビットアドレスの `reloc` を生成します。</span><span class="sxs-lookup"><span data-stu-id="dda11-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="dda11-118">64ビットアドレスの `reloc` を生成します。</span><span class="sxs-lookup"><span data-stu-id="dda11-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="dda11-119">Ia64 `br.call` 命令で25ビット PC 相対アドレスの `reloc` を生成します。</span><span class="sxs-lookup"><span data-stu-id="dda11-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="dda11-120">Ia64 `brl.call` 命令で64ビット PC 相対アドレスの `reloc` を生成します。</span><span class="sxs-lookup"><span data-stu-id="dda11-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="dda11-121">タグ付きポインター値に使用される、30ビットのセクション相対 `reloc`を生成します。</span><span class="sxs-lookup"><span data-stu-id="dda11-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="dda11-122">この列挙型への追加が内部 `reloc` 名配列に反映されるようにするための sentinel 値。</span><span class="sxs-lookup"><span data-stu-id="dda11-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="dda11-123">基本 `reloc`を生成しないように指定します。</span><span class="sxs-lookup"><span data-stu-id="dda11-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="dda11-124">メモリの事前修正の内容が、セクションオフセットではなくポインターであることを示す値。</span><span class="sxs-lookup"><span data-stu-id="dda11-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dda11-125">要件</span><span class="sxs-lookup"><span data-stu-id="dda11-125">Requirements</span></span>  
 <span data-ttu-id="dda11-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda11-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dda11-127">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="dda11-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dda11-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="dda11-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dda11-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dda11-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda11-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="dda11-130">See also</span></span>

- [<span data-ttu-id="dda11-131">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="dda11-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="dda11-132">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dda11-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="dda11-133">AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="dda11-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
