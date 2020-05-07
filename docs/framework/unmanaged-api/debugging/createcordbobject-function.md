---
title: CreateCordbObject 関数
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 340d2de09562ea9b767203a7fa839cdc6b729b3b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860888"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="3490a-102">CreateCordbObject 関数</span><span class="sxs-lookup"><span data-stu-id="3490a-102">CreateCordbObject Function</span></span>
<span data-ttu-id="3490a-103">リモートプロセスでマネージデバッグセッションをインスタンス化する機能を提供するデバッガーインターフェイス ([ICorDebug](icordebug-interface.md)) を作成します。</span><span class="sxs-lookup"><span data-stu-id="3490a-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3490a-104">構文</span><span class="sxs-lookup"><span data-stu-id="3490a-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3490a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3490a-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="3490a-106">[in] ターゲット プロセスのデバッガー バージョン。</span><span class="sxs-lookup"><span data-stu-id="3490a-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="3490a-107">リモート デバッグの場合、このパラメーターは CorDebugVersion_2_0 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3490a-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="3490a-108">入出力[ICorDebug](icordebug-interface.md)インターフェイスにキャストされて返されるオブジェクトへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3490a-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3490a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3490a-109">Return Value</span></span>  
 <span data-ttu-id="3490a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3490a-110">S_OK</span></span>  
 <span data-ttu-id="3490a-111">プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="3490a-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="3490a-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3490a-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="3490a-113">`ppCordb` が null であるか、または `iDebuggerVersion` が CorDebugVersion_2_0 ではありません。</span><span class="sxs-lookup"><span data-stu-id="3490a-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="3490a-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3490a-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="3490a-115">`ppCordb` 用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="3490a-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="3490a-116">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="3490a-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3490a-117">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3490a-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3490a-118">解説</span><span class="sxs-lookup"><span data-stu-id="3490a-118">Remarks</span></span>  
 <span data-ttu-id="3490a-119">で[ICorDebug](icordebug-interface.md) `ppCordb`返される ICorDebug インターフェイスは、すべてのマネージデバッグサービスの最上位レベルのデバッグインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="3490a-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3490a-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="3490a-120">Requirements</span></span>  
 <span data-ttu-id="3490a-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3490a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3490a-122">**ヘッダー:** Coreclrremoteデバッグインターフェイス .h</span><span class="sxs-lookup"><span data-stu-id="3490a-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="3490a-123">**Library:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="3490a-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="3490a-124">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3490a-124">**.NET Framework Versions:** 3.5 SP1</span></span>
