---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129194"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="4128c-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="4128c-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="4128c-103">現在のメソッドで非同期 await 操作のグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="4128c-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="4128c-104">各 yield オフセットは await の戻り命令に一致し、潜在的な yield を識別します。</span><span class="sxs-lookup"><span data-stu-id="4128c-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="4128c-105">各 `breakpointMethod`/`breakpointOffset` のペアによって、非同期操作が再開される場所がわかります。これは、別の方法で実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4128c-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4128c-106">構文</span><span class="sxs-lookup"><span data-stu-id="4128c-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4128c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4128c-107">Parameters</span></span>  
  
|<span data-ttu-id="4128c-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4128c-108">Parameter</span></span>|<span data-ttu-id="4128c-109">説明</span><span class="sxs-lookup"><span data-stu-id="4128c-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="4128c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="4128c-110">Return Value</span></span>  
 <span data-ttu-id="4128c-111">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="4128c-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4128c-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="4128c-112">Requirements</span></span>  
 <span data-ttu-id="4128c-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="4128c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4128c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4128c-114">See also</span></span>

- [<span data-ttu-id="4128c-115">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4128c-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
