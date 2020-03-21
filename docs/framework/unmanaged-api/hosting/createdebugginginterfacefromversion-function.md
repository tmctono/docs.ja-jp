---
title: CreateDebuggingInterfaceFromVersion 関数
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176449"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="04e1d-102">CreateDebuggingInterfaceFromVersion 関数</span><span class="sxs-lookup"><span data-stu-id="04e1d-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="04e1d-103">指定されたバージョン情報に基づいて[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="04e1d-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="04e1d-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="04e1d-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="04e1d-105">代わりに、共通言語ランタイム (CLR) 2.0 のインターフェイスを取得するには、[メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)を使用して、クラス識別子CLSID_CLRDebuggingLegacyとインターフェイス識別子IID_ICorDebugを指定します。</span><span class="sxs-lookup"><span data-stu-id="04e1d-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="04e1d-106">CLR 4 以降のインターフェイスを取得するには[、CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)関数を呼び出し、クラス識別子CLSID_CLRDebuggingとインターフェイス識別子IID_ICLRDebuggingを指定します。</span><span class="sxs-lookup"><span data-stu-id="04e1d-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04e1d-107">構文</span><span class="sxs-lookup"><span data-stu-id="04e1d-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04e1d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04e1d-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="04e1d-109">[in]`ICorDebug`デバッガーが予期するバージョンです。</span><span class="sxs-lookup"><span data-stu-id="04e1d-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="04e1d-110">有効な値については、[列挙](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04e1d-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="04e1d-111">[in]デバッグするアプリケーションまたはプロセスに関連付けられている共通言語ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="04e1d-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="04e1d-112">この値の[取得](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)の詳細については[、メソッドを](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="04e1d-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="04e1d-113">[アウト]`ICorDebug`オブジェクトへのポインターを受け取る位置。</span><span class="sxs-lookup"><span data-stu-id="04e1d-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04e1d-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="04e1d-114">Return Value</span></span>  
 <span data-ttu-id="04e1d-115">このメソッドは、WinError.h ファイルで定義されている標準 COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="04e1d-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="04e1d-116">リターン コード</span><span class="sxs-lookup"><span data-stu-id="04e1d-116">Return code</span></span>|<span data-ttu-id="04e1d-117">説明</span><span class="sxs-lookup"><span data-stu-id="04e1d-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="04e1d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="04e1d-118">S_OK</span></span>|<span data-ttu-id="04e1d-119">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="04e1d-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="04e1d-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="04e1d-120">E_INVALIDARG</span></span>|<span data-ttu-id="04e1d-121">`szDebuggeeVersion`または`ppCordb`null であるか、バージョン文字列が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="04e1d-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04e1d-122">解説</span><span class="sxs-lookup"><span data-stu-id="04e1d-122">Remarks</span></span>  
 <span data-ttu-id="04e1d-123">パラメーター`szDebuggeeVersion`は、対応するバージョンの MSCorDbi.dll にマップされます。</span><span class="sxs-lookup"><span data-stu-id="04e1d-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04e1d-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="04e1d-124">Requirements</span></span>  
 <span data-ttu-id="04e1d-125">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04e1d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04e1d-126">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04e1d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04e1d-127">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04e1d-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04e1d-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04e1d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e1d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="04e1d-129">See also</span></span>

- [<span data-ttu-id="04e1d-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="04e1d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
