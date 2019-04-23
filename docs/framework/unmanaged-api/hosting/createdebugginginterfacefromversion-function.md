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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d1c49e8762d00e3e154c598c2542c4a76b9b28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107498"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="cdab1-102">CreateDebuggingInterfaceFromVersion 関数</span><span class="sxs-lookup"><span data-stu-id="cdab1-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="cdab1-103">作成、 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)オブジェクトが指定されたバージョン情報に基づきます。</span><span class="sxs-lookup"><span data-stu-id="cdab1-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="cdab1-104">この関数は廃止されていますが、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cdab1-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="cdab1-105">代わりに、共通言語ランタイム (CLR) 2.0 のインターフェイスを取得、使用、 [iclrruntimeinfo::getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)メソッド CLSID_CLRDebuggingLegacy クラス識別子と IID_ICorDebug インターフェイス識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdab1-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="cdab1-106">CLR 4 のインターフェイスを取得します。 または、後で呼び出し、 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)関数とクラス識別子 CLSID_CLRDebugging と IID_ICLRDebugging インターフェイス識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdab1-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdab1-107">構文</span><span class="sxs-lookup"><span data-stu-id="cdab1-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdab1-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cdab1-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="cdab1-109">[in]バージョンの`ICorDebug`デバッガーによって必要なことができます。</span><span class="sxs-lookup"><span data-stu-id="cdab1-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="cdab1-110">参照してください、 [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)有効な値の列挙体。</span><span class="sxs-lookup"><span data-stu-id="cdab1-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="cdab1-111">[in]デバッグするには、アプリケーションまたはプロセスに関連付けられている、共通言語ランタイム バージョン。</span><span class="sxs-lookup"><span data-stu-id="cdab1-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="cdab1-112">参照してください、 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)または[GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)メソッドについては、この値を取得する方法。</span><span class="sxs-lookup"><span data-stu-id="cdab1-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="cdab1-113">[out]ポインターを受け取る場所、`ICorDebug`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cdab1-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdab1-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="cdab1-114">Return Value</span></span>  
 <span data-ttu-id="cdab1-115">このメソッドは、次の値だけでなく、WinError.h ファイルで定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="cdab1-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="cdab1-116">リターン コード</span><span class="sxs-lookup"><span data-stu-id="cdab1-116">Return code</span></span>|<span data-ttu-id="cdab1-117">説明</span><span class="sxs-lookup"><span data-stu-id="cdab1-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cdab1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="cdab1-118">S_OK</span></span>|<span data-ttu-id="cdab1-119">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="cdab1-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="cdab1-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cdab1-120">E_INVALIDARG</span></span>|<span data-ttu-id="cdab1-121">`szDebuggeeVersion` または`ppCordb`が null の場合、または、バージョン文字列が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="cdab1-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdab1-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdab1-122">Remarks</span></span>  
 <span data-ttu-id="cdab1-123">`szDebuggeeVersion` MSCorDbi.dll の対応するバージョンにパラメーターがマップされます。</span><span class="sxs-lookup"><span data-stu-id="cdab1-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdab1-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="cdab1-124">Requirements</span></span>  
 <span data-ttu-id="cdab1-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdab1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdab1-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cdab1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cdab1-127">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cdab1-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdab1-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdab1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdab1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdab1-129">See also</span></span>

- [<span data-ttu-id="cdab1-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="cdab1-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
