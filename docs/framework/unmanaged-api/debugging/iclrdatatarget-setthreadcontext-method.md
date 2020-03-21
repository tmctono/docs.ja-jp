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
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179125"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="f382f-102">ICLRDataTarget::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="f382f-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="f382f-103">ターゲット プロセス内の指定したスレッドの現在のコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="f382f-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="f382f-104">このメソッドは、共通言語ランタイム (CLR) のデータ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f382f-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f382f-105">構文</span><span class="sxs-lookup"><span data-stu-id="f382f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f382f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f382f-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f382f-107">[in]ターゲット プロセス内のスレッドのオペレーティング システム識別子。</span><span class="sxs-lookup"><span data-stu-id="f382f-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f382f-108">[in]コンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="f382f-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="f382f-109">[in]コンテキストを含むバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f382f-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="f382f-110">バッファー内の`context`データは、Win32`CONTEXT`構造体の形式になります。</span><span class="sxs-lookup"><span data-stu-id="f382f-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="f382f-111">コンテキストはプロセッサ固有のレジスタ データを指定するため、Win32`CONTEXT`構造体の定義はプロセッサのアーキテクチャによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f382f-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="f382f-112">Win32`CONTEXT`構造体の定義については、WinNT.h ヘッダー ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f382f-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f382f-113">解説</span><span class="sxs-lookup"><span data-stu-id="f382f-113">Remarks</span></span>  
 <span data-ttu-id="f382f-114">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="f382f-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f382f-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="f382f-115">Requirements</span></span>  
 <span data-ttu-id="f382f-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f382f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f382f-117">**ヘッダー:** をします。</span><span class="sxs-lookup"><span data-stu-id="f382f-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f382f-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f382f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f382f-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f382f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f382f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f382f-120">See also</span></span>

- [<span data-ttu-id="f382f-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f382f-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
