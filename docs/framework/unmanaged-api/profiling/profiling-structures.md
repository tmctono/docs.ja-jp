---
title: 構造体のプロファイリング
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 2f3e8cedcc498230311c0b52f7ecc1c2c4fc8ff1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447699"
---
# <a name="profiling-structures"></a><span data-ttu-id="52509-102">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="52509-102">Profiling Structures</span></span>
<span data-ttu-id="52509-103">このセクションではプロファイル API で使用されるアンマネージ構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="52509-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52509-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="52509-104">In This Section</span></span>  
 [<span data-ttu-id="52509-105">COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="52509-106">共通言語ランタイムに、アセンブリ参照クロージャー ウォークを実行するときに考慮するべき参照アセンブリに関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="52509-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="52509-107">COR_PRF_CODE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="52509-108">メモリに格納されている 1 個の連続ブロックからなるネイティブ コードを表します。</span><span class="sxs-lookup"><span data-stu-id="52509-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="52509-109">COR_PRF_EX_CLAUSE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="52509-110">特定の例外句インスタンスおよび関連するフレームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="52509-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="52509-111">COR_PRF_FUNCTION 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="52509-112">関数の一意の表記を、その関数の ID を再コンパイルされたバージョンの ID と組み合わせることによって、提供します。</span><span class="sxs-lookup"><span data-stu-id="52509-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="52509-113">COR_PRF_FUNCTION_ARGUMENT_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="52509-114">関数の引数を左から右方向で表します。</span><span class="sxs-lookup"><span data-stu-id="52509-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="52509-115">COR_PRF_FUNCTION_ARGUMENT_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="52509-116">メモリに左から右方向へ連続で格納される関数の引数のブロックを表します。</span><span class="sxs-lookup"><span data-stu-id="52509-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="52509-117">COR_PRF_GC_GENERATION_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="52509-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="52509-118">ガーベッジ コレクションを実行中のメモリ範囲 (ブロック) を説明します。</span><span class="sxs-lookup"><span data-stu-id="52509-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="52509-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="52509-119">Related Sections</span></span>  
 <span data-ttu-id="52509-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="52509-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="52509-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="52509-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="52509-122">プロファイルの概要</span><span class="sxs-lookup"><span data-stu-id="52509-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="52509-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="52509-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="52509-124">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="52509-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="52509-125">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="52509-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
