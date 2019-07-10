---
title: ICorDebugProcess::IsTransitionStub メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec29aa748c437199434fa1394e1a00c82154447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766876"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="bfc6c-102">ICorDebugProcess::IsTransitionStub メソッド</span><span class="sxs-lookup"><span data-stu-id="bfc6c-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="bfc6c-103">マネージ コードへの遷移を発生させるスタブ内にアドレスがあるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfc6c-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfc6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="bfc6c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfc6c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfc6c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bfc6c-106">[in]A`CORDB_ADDRESS`対象アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="bfc6c-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="bfc6c-107">[out]ブール値へのポインター`true`場合、マネージ コードへの遷移を発生させるスタブ内で指定されたアドレスは、それ以外の場合 \*`pbTransitionStub`は`false`。</span><span class="sxs-lookup"><span data-stu-id="bfc6c-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfc6c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bfc6c-108">Remarks</span></span>  
 <span data-ttu-id="bfc6c-109">`IsTransitionStub`をマネージ ステッパをステップ実行の制御を返すタイミングを決定するアンマネージ ステップ実行のコードでメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfc6c-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="bfc6c-110">こともできます identity 遷移スタブ ポータブル実行可能 (PE) ファイルに情報を参照しています。</span><span class="sxs-lookup"><span data-stu-id="bfc6c-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfc6c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bfc6c-111">Requirements</span></span>  
 <span data-ttu-id="bfc6c-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfc6c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfc6c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfc6c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfc6c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfc6c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfc6c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfc6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
