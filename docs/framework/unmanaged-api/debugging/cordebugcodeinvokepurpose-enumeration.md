---
title: CorDebugCodeInvokePurpose 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 858dfe9b15422680a261fef9e22d8c89d9d7fe45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609133"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="b375d-102">CorDebugCodeInvokePurpose 列挙体</span><span class="sxs-lookup"><span data-stu-id="b375d-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="b375d-103">エクスポートされた関数がマネージド コードを呼び出す理由を示します。</span><span class="sxs-lookup"><span data-stu-id="b375d-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b375d-104">構文</span><span class="sxs-lookup"><span data-stu-id="b375d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="b375d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b375d-105">Members</span></span>  
  
|<span data-ttu-id="b375d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b375d-106">Member</span></span>|<span data-ttu-id="b375d-107">説明</span><span class="sxs-lookup"><span data-stu-id="b375d-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="b375d-108">None または不明です。</span><span class="sxs-lookup"><span data-stu-id="b375d-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="b375d-109">マネージド コードは、逆 p-invoke などのすべてのマネージド エントリ ポイントを実行します。</span><span class="sxs-lookup"><span data-stu-id="b375d-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="b375d-110">より詳細な目的は、ランタイムによって認識されません。</span><span class="sxs-lookup"><span data-stu-id="b375d-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="b375d-111">マネージド コードは、静的コンストラクターを実行します。</span><span class="sxs-lookup"><span data-stu-id="b375d-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="b375d-112">マネージド コードは、呼び出されたいくつかのインターフェイス メソッドの実装を実行します。</span><span class="sxs-lookup"><span data-stu-id="b375d-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b375d-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="b375d-113">Remarks</span></span>  
 <span data-ttu-id="b375d-114">この列挙体を使って、 [icordebugprocess 6::getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)マネージ コードをステップ実行に関する情報を提供するメソッド。</span><span class="sxs-lookup"><span data-stu-id="b375d-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b375d-115">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="b375d-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b375d-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="b375d-116">Requirements</span></span>  
 <span data-ttu-id="b375d-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b375d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b375d-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b375d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b375d-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b375d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b375d-120">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b375d-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b375d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b375d-121">See also</span></span>

- [<span data-ttu-id="b375d-122">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="b375d-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="b375d-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b375d-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
