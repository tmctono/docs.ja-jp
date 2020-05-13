---
title: ICorDebugFrame::GetStackRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205156"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="69f2a-102">ICorDebugFrame::GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="69f2a-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="69f2a-103">このスタックフレームの絶対アドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="69f2a-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69f2a-104">構文</span><span class="sxs-lookup"><span data-stu-id="69f2a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69f2a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="69f2a-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="69f2a-106">入出力`CORDB_ADDRESS`このオブジェクトによって表されるスタックフレームの開始アドレスを指定するへのポインター `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="69f2a-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="69f2a-107">入出力`CORDB_ADDRESS`このオブジェクトによって表されるスタックフレームの終了アドレスを指定するへのポインター `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="69f2a-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69f2a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="69f2a-108">Remarks</span></span>  
 <span data-ttu-id="69f2a-109">スタックのアドレス範囲は、複数のデバッグエンジンから収集されたインターリーブスタックトレースを piecing する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="69f2a-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="69f2a-110">数値の範囲は、スタックフレームの内容に関する情報を提供しません。</span><span class="sxs-lookup"><span data-stu-id="69f2a-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="69f2a-111">スタックフレームの位置を比較する場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="69f2a-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69f2a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="69f2a-112">Requirements</span></span>  
 <span data-ttu-id="69f2a-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f2a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69f2a-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69f2a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69f2a-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69f2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69f2a-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69f2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
