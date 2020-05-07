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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860611"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="889bc-102">ICLRDataTarget::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="889bc-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="889bc-103">ターゲットプロセス内の指定されたスレッドの現在の実行コンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="889bc-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="889bc-104">このメソッドは、共通言語ランタイムのデータアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="889bc-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="889bc-105">構文</span><span class="sxs-lookup"><span data-stu-id="889bc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="889bc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="889bc-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="889bc-107">からターゲットプロセス内のスレッドのオペレーティングシステム識別子。</span><span class="sxs-lookup"><span data-stu-id="889bc-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="889bc-108">からコンテキストのどの部分を返すかを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="889bc-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="889bc-109">実装は、少なくともこれらのコンテキストの部分を返します。</span><span class="sxs-lookup"><span data-stu-id="889bc-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="889bc-110">からコンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="889bc-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="889bc-111">入出力コンテキストを配置するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="889bc-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="889bc-112">`context`バッファー内のデータは、Win32 `CONTEXT`構造体の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="889bc-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="889bc-113">コンテキストはプロセッサ固有のレジスタデータを指定するため、Win32 `CONTEXT`構造体の定義はプロセッサのアーキテクチャによって異なります。</span><span class="sxs-lookup"><span data-stu-id="889bc-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="889bc-114">Win32 `CONTEXT`構造体の定義については、winnt.h ヘッダーファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="889bc-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="889bc-115">解説</span><span class="sxs-lookup"><span data-stu-id="889bc-115">Remarks</span></span>  
 <span data-ttu-id="889bc-116">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="889bc-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="889bc-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="889bc-117">Requirements</span></span>  
 <span data-ttu-id="889bc-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="889bc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="889bc-119">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="889bc-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="889bc-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="889bc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="889bc-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="889bc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="889bc-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="889bc-122">See also</span></span>

- [<span data-ttu-id="889bc-123">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="889bc-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
