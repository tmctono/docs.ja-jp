---
title: ICLRDataTarget::GetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179176"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="02ac0-102">ICLRDataTarget::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="02ac0-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="02ac0-103">ターゲット プロセス内の特定のスレッドの現在の実行コンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="02ac0-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="02ac0-104">このメソッドは、共通言語ランタイムのデータ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="02ac0-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ac0-105">構文</span><span class="sxs-lookup"><span data-stu-id="02ac0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02ac0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="02ac0-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="02ac0-107">[in]ターゲット プロセス内のスレッドのオペレーティング システム識別子。</span><span class="sxs-lookup"><span data-stu-id="02ac0-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="02ac0-108">[in]コンテキストのどの部分を返すかを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="02ac0-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="02ac0-109">実装は、少なくともコンテキストのこれらの部分を返します。</span><span class="sxs-lookup"><span data-stu-id="02ac0-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="02ac0-110">[in]コンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="02ac0-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="02ac0-111">[アウト]コンテキストを配置するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="02ac0-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="02ac0-112">バッファー内の`context`データは、Win32`CONTEXT`構造体の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02ac0-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="02ac0-113">コンテキストはプロセッサ固有のレジスタ データを指定するため、Win32`CONTEXT`構造体の定義はプロセッサのアーキテクチャによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02ac0-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="02ac0-114">Win32`CONTEXT`構造体の定義については、WinNT.h ヘッダー ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ac0-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02ac0-115">解説</span><span class="sxs-lookup"><span data-stu-id="02ac0-115">Remarks</span></span>  
 <span data-ttu-id="02ac0-116">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="02ac0-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ac0-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="02ac0-117">Requirements</span></span>  
 <span data-ttu-id="02ac0-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ac0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ac0-119">**ヘッダー:** をします。</span><span class="sxs-lookup"><span data-stu-id="02ac0-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="02ac0-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02ac0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02ac0-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ac0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ac0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="02ac0-122">See also</span></span>

- [<span data-ttu-id="02ac0-123">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02ac0-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
