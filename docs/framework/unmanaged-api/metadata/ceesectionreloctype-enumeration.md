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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176215"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="9f6f1-102">CeeSectionRelocType 列挙型</span><span class="sxs-lookup"><span data-stu-id="9f6f1-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="9f6f1-103">`reloc` [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)の呼び出しで出力される命令の種類に影響を与える値を提供します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f6f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f6f1-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9f6f1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9f6f1-105">Members</span></span>  
  
|<span data-ttu-id="9f6f1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9f6f1-106">Member</span></span>|<span data-ttu-id="9f6f1-107">説明</span><span class="sxs-lookup"><span data-stu-id="9f6f1-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="9f6f1-108">セクション相対`reloc`部分だけを生成し、.reloc セクションに何も送信しません。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="9f6f1-109">ポインター サイズ`reloc`の場所の を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="9f6f1-110">これは、プラットフォームに応じてBASED_HIGHLOWまたはBASED_DIR64に変換されます。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="9f6f1-111">32`reloc`ビットの数値の上位 16 ビットに対して a を生成し、下の 16 ビットが .reloc テーブルの次の単語に含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="9f6f1-112">トークン マップの再配置を生成し、.reloc セクションに何も送信しません。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="9f6f1-113">値が相対アドレスフィックスアップであることを示します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="9f6f1-114">セクション相対`reloc`部分だけを生成し、.reloc セクションに何も送信しません。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="9f6f1-115">これは`reloc`セクションの仮想アドレスではなく、セクションのファイル位置を基準にしています。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="9f6f1-116">コード相対アドレスのフィックスアップを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="9f6f1-117">ia64`reloc``movl`命令で 64 ビットアドレスの a を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="9f6f1-118">64`reloc`ビット アドレスの を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="9f6f1-119">`reloc` ia64`br.call`命令で 25 ビット PC 相対アドレスの を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="9f6f1-120">ia64`reloc``brl.call`命令で 64 ビット PC 相対アドレスの a を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="9f6f1-121">タグ付きポインター値に使用される 30 ビットのセクション相対`reloc`値を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="9f6f1-122">この列挙型への追加が内部`reloc`の名前配列に反映されることを確認するのに役立つセンチネル値。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="9f6f1-123">ベース`reloc`を出力しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="9f6f1-124">メモリの修正前の内容がセクション オフセットではなくポインターであることを示す値。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f6f1-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f6f1-125">Requirements</span></span>  
 <span data-ttu-id="9f6f1-126">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f6f1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f6f1-127">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="9f6f1-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f6f1-128">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="9f6f1-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f6f1-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f6f1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6f1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f6f1-130">See also</span></span>

- [<span data-ttu-id="9f6f1-131">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="9f6f1-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="9f6f1-132">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f6f1-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="9f6f1-133">AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f1-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
