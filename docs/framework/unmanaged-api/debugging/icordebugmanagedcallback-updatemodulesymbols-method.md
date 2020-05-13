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
ms.openlocfilehash: 9ee6f43c94b8ff2e765d2a0dde0697c4c895a94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212374"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="8a7b9-102">ICorDebugManagedCallback::UpdateModuleSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="8a7b9-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="8a7b9-103">共通言語ランタイムモジュールのシンボルが変更されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a7b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a7b9-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a7b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a7b9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8a7b9-106">からシンボルが変更されたモジュールを含むアプリケーションドメインを表す、コードのオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="8a7b9-107">からシンボルが変更されたモジュールを表す、のモジュールオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="8a7b9-108">から変更されたシンボルを格納している Win32 COM オブジェクトへのポインター `IStream` 。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a7b9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a7b9-109">Remarks</span></span>  
 <span data-ttu-id="8a7b9-110">このメソッドは、 [ISymUnmanagedReader::::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) ISymUnmanagedReader [:::: 置き換え esyman store](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md)を呼び出すことによって、モジュールのシンボルのデバッガービューを更新する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="8a7b9-111">このコールバックは、同じモジュールに対して複数回発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="8a7b9-112">デバッガーは、バインドされていないソースレベルのブレークポイントをバインドしようとします。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a7b9-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a7b9-113">Requirements</span></span>  
 <span data-ttu-id="8a7b9-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a7b9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a7b9-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a7b9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a7b9-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a7b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a7b9-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a7b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7b9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a7b9-118">See also</span></span>

- [<span data-ttu-id="8a7b9-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a7b9-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
