---
title: ICorDebugAssembly3::EnumerateContainedAssemblies メソッド
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05c4e2a5c16f11f80cc8356a65b746eab81a3899
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744403"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="4f107-102">ICorDebugAssembly3::EnumerateContainedAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="4f107-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="4f107-103">このアセンブリに含まれているアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f107-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f107-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f107-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f107-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f107-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="4f107-106">[out]列挙子である ICorDebugAssemblyEnum インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f107-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f107-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4f107-107">Return Value</span></span>  
 <span data-ttu-id="4f107-108">この `S_OK` オブジェクトがコンテナーの場合は、`ICorDebugAssembly3`。それ以外の場合は、`S_FALSE` で、列挙子は空です。</span><span class="sxs-lookup"><span data-stu-id="4f107-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f107-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f107-109">Remarks</span></span>  
 <span data-ttu-id="4f107-110">含まれているアセンブリを列挙するためにシンボルが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f107-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="4f107-111">シンボルがない場合、メソッドは `S_FALSE` を返し、有効な列挙子は提供されません。</span><span class="sxs-lookup"><span data-stu-id="4f107-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f107-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f107-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f107-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f107-113">Requirements</span></span>  
 <span data-ttu-id="4f107-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f107-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f107-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f107-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f107-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f107-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f107-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f107-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f107-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f107-118">See also</span></span>

- [<span data-ttu-id="4f107-119">ICorDebugAssembly3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f107-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="4f107-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f107-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
