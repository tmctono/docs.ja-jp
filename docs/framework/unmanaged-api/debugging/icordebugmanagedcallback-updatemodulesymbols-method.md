---
title: ICorDebugManagedCallback::UpdateModuleSymbols メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 2b64122489481c6b0fde605015720d0a56ba8fe2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788323"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="e26d7-102">ICorDebugManagedCallback::UpdateModuleSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="e26d7-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="e26d7-103">共通言語ランタイムモジュールのシンボルが変更されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e26d7-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="e26d7-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e26d7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e26d7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e26d7-106">からシンボルが変更されたモジュールを含むアプリケーションドメインを表す、コードのオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e26d7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="e26d7-107">からシンボルが変更されたモジュールを表す、のモジュールオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e26d7-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="e26d7-108">から変更されたシンボルを格納している Win32 COM `IStream` オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e26d7-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e26d7-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e26d7-109">Remarks</span></span>  
 <span data-ttu-id="e26d7-110">このメソッドは、 [ISymUnmanagedReader::::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) ISymUnmanagedReader [:::: 置き換え esyman store](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)を呼び出すことによって、モジュールのシンボルのデバッガービューを更新する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="e26d7-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="e26d7-111">このコールバックは、同じモジュールに対して複数回発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e26d7-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="e26d7-112">デバッガーは、バインドされていないソースレベルのブレークポイントをバインドしようとします。</span><span class="sxs-lookup"><span data-stu-id="e26d7-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e26d7-113">要件</span><span class="sxs-lookup"><span data-stu-id="e26d7-113">Requirements</span></span>  
 <span data-ttu-id="e26d7-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e26d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e26d7-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e26d7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e26d7-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e26d7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e26d7-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e26d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26d7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e26d7-118">See also</span></span>

- [<span data-ttu-id="e26d7-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e26d7-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
