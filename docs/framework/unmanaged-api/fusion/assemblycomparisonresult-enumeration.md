---
title: AssemblyComparisonResult 列挙型
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178290"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="f0762-102">AssemblyComparisonResult 列挙型</span><span class="sxs-lookup"><span data-stu-id="f0762-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="f0762-103">[2](compareassemblyidentity-function.md)つのアセンブリ ID の等価性を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0762-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0762-104">Syntax</span></span>  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="f0762-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f0762-105">Members</span></span>  
  
|<span data-ttu-id="f0762-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="f0762-106">Member name</span></span>|<span data-ttu-id="f0762-107">説明</span><span class="sxs-lookup"><span data-stu-id="f0762-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="f0762-108">比較内のすべてのアセンブリ フィールドが一致することを示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="f0762-109">.NET Framework バージョン 2.0 のアセンブリ バージョン番号の共通言語ランタイム バージョン (CLR) の統一に基づいて、アセンブリが等価と見なされることを示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="f0762-110">.NET Framework 2.0 のアセンブリ バージョン番号の CLR 統合に基づいて、アセンブリの部分的な一致を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="f0762-111">アセンブリの部分的な一致を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="f0762-112">バージョン番号のレガシ統一に基づいてアセンブリの部分的一致を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="f0762-113">名前付きのアセンブリの部分一致を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="f0762-114">アセンブリが、.NET Framework のレガシ バージョンのバージョン番号の CLR 統合に基づいて等価であると見なされることを示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="f0762-115">バージョン番号が無視された 2 つの単純な名前付きアセンブリ間の一致を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="f0762-116">2 つのアセンブリ間で一致が発生しなかった場合を示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="f0762-117">バージョン番号が部分的にしか一致しない場合は、2 つのアセンブリが一致することを示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="f0762-118">2 つのアセンブリが、バージョン番号が一致しない場合を除いて一致することを示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="f0762-119">非等価性の理由が不明であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f0762-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0762-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0762-120">Requirements</span></span>  
 <span data-ttu-id="f0762-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0762-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0762-122">**ヘッダー:** フュージョン.h</span><span class="sxs-lookup"><span data-stu-id="f0762-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f0762-123">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="f0762-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f0762-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0762-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0762-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0762-125">See also</span></span>

- [<span data-ttu-id="f0762-126">CompareAssemblyIdentity 関数</span><span class="sxs-lookup"><span data-stu-id="f0762-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="f0762-127">fusion 列挙体</span><span class="sxs-lookup"><span data-stu-id="f0762-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
