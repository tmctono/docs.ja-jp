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
ms.openlocfilehash: b8c4b4e585bba4df39a743273221f38ce14a9b9d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860532"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="8c93c-102">ICLRDataTarget::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="8c93c-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="8c93c-103">ターゲットプロセス内の指定されたスレッドの現在のコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="8c93c-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="8c93c-104">このメソッドは、共通言語ランタイム (CLR) データアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8c93c-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c93c-105">構文</span><span class="sxs-lookup"><span data-stu-id="8c93c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c93c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c93c-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8c93c-107">からターゲットプロセス内のスレッドのオペレーティングシステム識別子。</span><span class="sxs-lookup"><span data-stu-id="8c93c-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8c93c-108">からコンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8c93c-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="8c93c-109">からコンテキストを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8c93c-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="8c93c-110">`context`バッファー内のデータは、Win32 `CONTEXT`構造体の形式になります。</span><span class="sxs-lookup"><span data-stu-id="8c93c-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="8c93c-111">コンテキストはプロセッサ固有のレジスタデータを指定するため、Win32 `CONTEXT`構造体の定義はプロセッサのアーキテクチャによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8c93c-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="8c93c-112">Win32 `CONTEXT`構造体の定義については、winnt.h ヘッダーファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c93c-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c93c-113">解説</span><span class="sxs-lookup"><span data-stu-id="8c93c-113">Remarks</span></span>  
 <span data-ttu-id="8c93c-114">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="8c93c-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c93c-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c93c-115">Requirements</span></span>  
 <span data-ttu-id="8c93c-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c93c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c93c-117">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="8c93c-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8c93c-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c93c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c93c-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c93c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c93c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c93c-120">See also</span></span>

- [<span data-ttu-id="8c93c-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c93c-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
