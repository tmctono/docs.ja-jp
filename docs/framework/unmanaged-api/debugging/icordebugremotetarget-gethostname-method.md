---
title: ICorDebugRemoteTarget::GetHostName メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: f177d441da3bd967750781e487d9fed42bc132f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791946"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="cd170-102">ICorDebugRemoteTarget::GetHostName メソッド</span><span class="sxs-lookup"><span data-stu-id="cd170-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="cd170-103">リモート デバッグ対象コンピューターの完全修飾ドメイン名または IPv4 アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="cd170-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="cd170-104">IPV6 はこの時点ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="cd170-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd170-105">構文</span><span class="sxs-lookup"><span data-stu-id="cd170-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd170-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd170-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="cd170-107">[入力] `szHostName` バッファーのサイズ (文字単位)。</span><span class="sxs-lookup"><span data-stu-id="cd170-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="cd170-108">このパラメーターが 0 である場合、`szHostName` は null であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd170-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="cd170-109">[出力] 配列に返される文字数。ホスト名または IP アドレスの null 終端文字を含みます。</span><span class="sxs-lookup"><span data-stu-id="cd170-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="cd170-110">このパラメーターは、null でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="cd170-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="cd170-111">[出力] ホスト名または IP アドレスを含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="cd170-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd170-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="cd170-112">Return Value</span></span>  
 <span data-ttu-id="cd170-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd170-113">S_OK</span></span>  
 <span data-ttu-id="cd170-114">ホスト名または IP アドレスは正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="cd170-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="cd170-115">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="cd170-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="cd170-116">ホスト名または IP アドレスを返すことができません。</span><span class="sxs-lookup"><span data-stu-id="cd170-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd170-117">コメント</span><span class="sxs-lookup"><span data-stu-id="cd170-117">Remarks</span></span>  
 <span data-ttu-id="cd170-118">このメソッドは、デバッガー ライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="cd170-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="cd170-119">これは、複数の呼び出しパラダイムに従う必要があります。最初の呼び出しでは、呼び出し元は null を `cchHostName` と `szHostName`の両方に渡し、`pcchHostName` は必要なバッファーのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="cd170-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="cd170-120">第 2 の呼び出しでは、以前に返されたサイズが `cchHostName` に渡され、適切にサイズ設定されたバッファーが `szHostName` に渡されます。</span><span class="sxs-lookup"><span data-stu-id="cd170-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd170-121">要件</span><span class="sxs-lookup"><span data-stu-id="cd170-121">Requirements</span></span>  
 <span data-ttu-id="cd170-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd170-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd170-123">**ヘッダー:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="cd170-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="cd170-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd170-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd170-125">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="cd170-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd170-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd170-126">See also</span></span>

- [<span data-ttu-id="cd170-127">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd170-127">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="cd170-128">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd170-128">ICorDebug Interface</span></span>](icordebug-interface.md)
