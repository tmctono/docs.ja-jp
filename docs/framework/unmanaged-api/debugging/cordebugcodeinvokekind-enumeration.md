---
title: CorDebugCodeInvokeKind 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3b4906f988d09f7b01aee40e8f63b589da5f33d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609205"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="8c476-102">CorDebugCodeInvokeKind 列挙体</span><span class="sxs-lookup"><span data-stu-id="8c476-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="8c476-103">エクスポートされた関数がマネージド コードを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c476-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c476-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c476-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="8c476-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c476-105">Members</span></span>  
  
|<span data-ttu-id="8c476-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c476-106">Member</span></span>|<span data-ttu-id="8c476-107">説明</span><span class="sxs-lookup"><span data-stu-id="8c476-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="8c476-108">マネージド コードがこのメソッドによって呼び出される場合は、明示的なイベントまたはブレークポイントによって後で配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c476-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="8c476-109">または</span><span class="sxs-lookup"><span data-stu-id="8c476-109">--or--</span></span><br /><br /> <span data-ttu-id="8c476-110">このメソッドが呼び出すマネージド コードは、停止する簡単な方法がないため、一部を見逃す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c476-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="8c476-111">または</span><span class="sxs-lookup"><span data-stu-id="8c476-111">--or--</span></span><br /><br /> <span data-ttu-id="8c476-112">メソッドがマネージド コードを呼び出さない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c476-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="8c476-113">このメソッドは、戻り命令を使用してマネージド コードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c476-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="8c476-114">ステップ アウトは次のマネージド コードに到達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c476-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="8c476-115">このメソッドは、末尾呼び出しを使用してマネージド コードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c476-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="8c476-116">いずれかの呼び出し命令をシングル ステップ実行およびステップ オーバーすると、マネージド コードに到達します。</span><span class="sxs-lookup"><span data-stu-id="8c476-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c476-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c476-117">Remarks</span></span>  
 <span data-ttu-id="8c476-118">この列挙体を使って、 [icordebugprocess 6::getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)マネージ コードをステップ実行に関する情報を提供するメソッド。</span><span class="sxs-lookup"><span data-stu-id="8c476-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c476-119">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="8c476-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c476-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c476-120">Requirements</span></span>  
 <span data-ttu-id="8c476-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c476-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c476-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c476-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c476-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c476-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c476-124">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c476-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c476-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c476-125">See also</span></span>

- [<span data-ttu-id="8c476-126">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="8c476-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="8c476-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="8c476-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
