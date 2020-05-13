---
title: CreateDebuggingInterfaceFromVersion 関数 (Silverlight 用)
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: f40345b09cae164660711b987f62130518736518
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208625"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="3babb-102">CreateDebuggingInterfaceFromVersion 関数 (Silverlight 用)</span><span class="sxs-lookup"><span data-stu-id="3babb-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>

<span data-ttu-id="3babb-103">[Createversionstringfrommodule 関数](createversionstringfrommodule-function.md)から返される共通言語ランタイム (CLR) のバージョン文字列を受け取り、対応するデバッガーインターフェイス (通常は[ICorDebug](icordebug-interface.md)) を返します。</span><span class="sxs-lookup"><span data-stu-id="3babb-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3babb-104">構文</span><span class="sxs-lookup"><span data-stu-id="3babb-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3babb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3babb-105">Parameters</span></span>  

 `szDebuggeeVersion`\
 <span data-ttu-id="3babb-106">から[Createversionstringfrommodule 関数](createversionstringfrommodule-function.md)によって返される、ターゲットデバッグ対象の CLR のバージョン文字列。</span><span class="sxs-lookup"><span data-stu-id="3babb-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`\
 <span data-ttu-id="3babb-107">[out] COM オブジェクト (`IUnknown`) へのポインターのポインター。</span><span class="sxs-lookup"><span data-stu-id="3babb-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="3babb-108">このオブジェクトは、返される前に[ICorDebug](icordebug-interface.md)オブジェクトにキャストされます。</span><span class="sxs-lookup"><span data-stu-id="3babb-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3babb-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3babb-109">Return Value</span></span>

 `S_OK`\
 <span data-ttu-id="3babb-110">`ppCordb`[ICorDebug インターフェイス](icordebug-interface.md)インターフェイスを実装する有効なオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="3babb-110">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 `E_INVALIDARG`\
 <span data-ttu-id="3babb-111">`szDebuggeeVersion` または `ppCordb` が null です。</span><span class="sxs-lookup"><span data-stu-id="3babb-111">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 <span data-ttu-id="3babb-112">CLR デバッグに必要なコンポーネントが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="3babb-112">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="3babb-113">_Mscordbi.dll_または_mscordaccore.dll が対象_のいずれかがターゲットの CoreCLR .dll と同じディレクトリに見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="3babb-113">Either _mscordbi.dll_ or _mscordaccore.dll_ was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 <span data-ttu-id="3babb-114">mscordbi.dll または mscordaccore.dll が対象の CoreCLR.dll と同じバージョンではありません。</span><span class="sxs-lookup"><span data-stu-id="3babb-114">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="3babb-115">`E_FAIL`(またはその他の `E_` リターンコード) </span><span class="sxs-lookup"><span data-stu-id="3babb-115">`E_FAIL` (or other `E_` return codes)</span></span>\
 <span data-ttu-id="3babb-116">[ICorDebug インターフェイス](icordebug-interface.md)を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="3babb-116">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3babb-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="3babb-117">Remarks</span></span>

 <span data-ttu-id="3babb-118">返されるインターフェイスは、対象のプロセス内の CLR にアタッチして CLR が実行しているマネージド コードをデバッグする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3babb-118">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3babb-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="3babb-119">Requirements</span></span>

 <span data-ttu-id="3babb-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3babb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3babb-121">**ヘッダー:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="3babb-121">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="3babb-122">**ライブラリ:** dbgshim .dll</span><span class="sxs-lookup"><span data-stu-id="3babb-122">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="3babb-123">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3babb-123">**.NET Framework Versions:** 3.5 SP1</span></span>
