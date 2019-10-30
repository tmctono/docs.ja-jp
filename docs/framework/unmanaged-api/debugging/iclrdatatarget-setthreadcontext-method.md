---
title: ICLRDataTarget::SetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: cceafc8358ce2b0eafa62a3855c4eb1e96adae11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113311"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="c9be7-102">ICLRDataTarget::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="c9be7-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="c9be7-103">ターゲットプロセス内の指定されたスレッドの現在のコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9be7-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="c9be7-104">このメソッドは、共通言語ランタイム (CLR) データアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c9be7-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9be7-105">構文</span><span class="sxs-lookup"><span data-stu-id="c9be7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9be7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9be7-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c9be7-107">からターゲットプロセス内のスレッドのオペレーティングシステム識別子。</span><span class="sxs-lookup"><span data-stu-id="c9be7-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c9be7-108">からコンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c9be7-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="c9be7-109">からコンテキストを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c9be7-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="c9be7-110">`context` バッファー内のデータは、Win32 `CONTEXT` 構造の形式になります。</span><span class="sxs-lookup"><span data-stu-id="c9be7-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="c9be7-111">コンテキストはプロセッサ固有のレジスタデータを指定するため、Win32 `CONTEXT` 構造体の定義は、プロセッサのアーキテクチャによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c9be7-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="c9be7-112">Win32 `CONTEXT` 構造の定義については、Winnt.h ヘッダーファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9be7-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9be7-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9be7-113">Remarks</span></span>  
 <span data-ttu-id="c9be7-114">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="c9be7-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9be7-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="c9be7-115">Requirements</span></span>  
 <span data-ttu-id="c9be7-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9be7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9be7-117">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="c9be7-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c9be7-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9be7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9be7-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9be7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9be7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9be7-120">See also</span></span>

- [<span data-ttu-id="c9be7-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9be7-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
