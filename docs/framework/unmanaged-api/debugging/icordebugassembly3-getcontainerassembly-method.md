---
title: ICorDebugAssembly3::GetContainerAssembly メソッド
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 068a08d70f2443edfe0970ec1ffb8cba9953c6b9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894848"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="3695b-102">ICorDebugAssembly3::GetContainerAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="3695b-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="3695b-103">この `ICorDebugAssembly3` オブジェクトのコンテナー アセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="3695b-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3695b-104">構文</span><span class="sxs-lookup"><span data-stu-id="3695b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3695b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3695b-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="3695b-106">コンテナーアセンブリを表す、オブジェクトのアドレスへのポインター。メソッドの呼び出しが失敗した場合は**null** 。</span><span class="sxs-lookup"><span data-stu-id="3695b-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3695b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3695b-107">Return Value</span></span>  
 <span data-ttu-id="3695b-108">`S_OK`メソッドの呼び出しが成功した場合は。それ以外`S_FALSE`の場合`ppAssembly` 、、、およびは**null**になります。</span><span class="sxs-lookup"><span data-stu-id="3695b-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3695b-109">解説</span><span class="sxs-lookup"><span data-stu-id="3695b-109">Remarks</span></span>  
 <span data-ttu-id="3695b-110">このアセンブリが 1 つのコンテナー アセンブリ内の他のアセンブリとマージされている場合、このメソッドはコンテナー アセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="3695b-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="3695b-111">詳細と用語については、「 [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3695b-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3695b-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3695b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3695b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="3695b-113">Requirements</span></span>  
 <span data-ttu-id="3695b-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3695b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3695b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3695b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3695b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3695b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3695b-117">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3695b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3695b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3695b-118">See also</span></span>

- [<span data-ttu-id="3695b-119">ICorDebugAssembly3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3695b-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="3695b-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3695b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
