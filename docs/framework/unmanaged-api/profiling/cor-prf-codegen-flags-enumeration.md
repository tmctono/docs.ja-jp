---
title: COR_PRF_CODEGEN_FLAGS 列挙体
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775129"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="31e30-102">COR_PRF_CODEGEN_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="31e30-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="31e30-103">設定可能なコード生成フラグを定義、 [icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="31e30-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31e30-104">構文</span><span class="sxs-lookup"><span data-stu-id="31e30-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="31e30-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="31e30-105">Members</span></span>  
  
|<span data-ttu-id="31e30-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="31e30-106">Member</span></span>|<span data-ttu-id="31e30-107">説明</span><span class="sxs-lookup"><span data-stu-id="31e30-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="31e30-108">関数はこの関数の本体にインライン化されません。</span><span class="sxs-lookup"><span data-stu-id="31e30-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="31e30-109">ただし、関数自体は、呼び出し元にインライン化でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31e30-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="31e30-110">この関数の本体のすべての最適化を無効化されます。</span><span class="sxs-lookup"><span data-stu-id="31e30-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="31e30-111">ただし、関数自体できない可能性がありますが、呼び出し元にインライン化します。</span><span class="sxs-lookup"><span data-stu-id="31e30-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31e30-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="31e30-112">Remarks</span></span>  
 <span data-ttu-id="31e30-113">`COR_PRF_CODEGEN_FLAGS`列挙型を使用して、 [icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)メソッドを JIT 再コンパイルされた関数のコード生成を制御するプロファイラーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="31e30-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31e30-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="31e30-114">Requirements</span></span>  
 <span data-ttu-id="31e30-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31e30-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31e30-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31e30-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31e30-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31e30-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31e30-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31e30-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e30-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="31e30-119">See also</span></span>

- [<span data-ttu-id="31e30-120">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="31e30-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
