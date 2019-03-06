---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bac541909e07aadff06006fba8c3cfcf4dc5465
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486226"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="2d351-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="2d351-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="2d351-103">非同期のグループを定義、現在のメソッドでの操作を待機します。</span><span class="sxs-lookup"><span data-stu-id="2d351-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="2d351-104">各 yield オフセットでは、潜在的な yield を識別する、await の戻り命令と一致します。</span><span class="sxs-lookup"><span data-stu-id="2d351-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="2d351-105">各`breakpointMethod` / `breakpointOffset`ペアによるメソッドが異なる可能性があるを非同期操作が再開されます。</span><span class="sxs-lookup"><span data-stu-id="2d351-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d351-106">構文</span><span class="sxs-lookup"><span data-stu-id="2d351-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d351-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d351-107">Parameters</span></span>  
  
|<span data-ttu-id="2d351-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d351-108">Parameter</span></span>|<span data-ttu-id="2d351-109">説明</span><span class="sxs-lookup"><span data-stu-id="2d351-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="2d351-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="2d351-110">Return Value</span></span>  
 <span data-ttu-id="2d351-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="2d351-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d351-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d351-112">Requirements</span></span>  
 <span data-ttu-id="2d351-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d351-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d351-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d351-114">See also</span></span>
- [<span data-ttu-id="2d351-115">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d351-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
