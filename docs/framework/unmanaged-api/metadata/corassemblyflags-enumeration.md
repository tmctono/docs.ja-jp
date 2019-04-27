---
title: CorAssemblyFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906244"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="0d6fa-102">CorAssemblyFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="0d6fa-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="0d6fa-103">アセンブリ コンパイルに適用されるメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d6fa-104">Syntax</span></span>  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0d6fa-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0d6fa-105">Members</span></span>  
  
|<span data-ttu-id="0d6fa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0d6fa-106">Member</span></span>|<span data-ttu-id="0d6fa-107">説明</span><span class="sxs-lookup"><span data-stu-id="0d6fa-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="0d6fa-108">アセンブリ参照が、ハッシュされていない完全な公開キーを保持していることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="0d6fa-109">プロセッサ アーキテクチャが指定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="0d6fa-110">プロセッサ アーキテクチャがニュートラルであることを示します (PE32)。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="0d6fa-111">プロセッサ アーキテクチャは、x86 (PE32) であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="0d6fa-112">プロセッサ アーキテクチャは、Itanium (pe 32 +) であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="0d6fa-113">プロセッサ アーキテクチャは、AMD X64 (pe 32 +) であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="0d6fa-114">プロセッサ アーキテクチャは、ARM (PE32) であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="0d6fa-115">アセンブリが参照アセンブリであることを示しますつまり、すべてのアーキテクチャに適用されますが、任意のアーキテクチャ上で実行できません。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="0d6fa-116">したがってと同じでは、フラグ`afPA_Mask`します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="0d6fa-117">プロセッサ アーキテクチャのフラグに反映させるかを示す、`AssemblyRef`レコード。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="0d6fa-118">プロセッサ アーキテクチャを示すマスク。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="0d6fa-119">プロセッサ アーキテクチャの説明が含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="0d6fa-120">プロセッサ アーキテクチャのフラグと、インデックスの間でシフト数を示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="0d6fa-121">対応する値を示します、<xref:System.Diagnostics.DebuggableAttribute.DebuggingModes>の<xref:System.Diagnostics.DebuggableAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="0d6fa-122">対応する値を示します、<xref:System.Diagnostics.DebuggableAttribute.DebuggingModes>の<xref:System.Diagnostics.DebuggableAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="0d6fa-123">実行時に、別の発行者からのアセンブリにアセンブリを再ターゲットできることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="0d6fa-124">コンテンツの種類を示すマスク。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="0d6fa-125">既定のコンテンツ タイプを示します。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="0d6fa-126">示す、[!INCLUDE[wrt](../../../../includes/wrt-md.md)]コンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d6fa-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d6fa-127">Requirements</span></span>  
 <span data-ttu-id="0d6fa-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d6fa-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6fa-129">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0d6fa-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0d6fa-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d6fa-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6fa-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d6fa-131">See also</span></span>

- [<span data-ttu-id="0d6fa-132">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="0d6fa-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
