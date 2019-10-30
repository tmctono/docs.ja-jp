---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129172"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="aa687-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="aa687-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="aa687-103">非同期操作を開始する開始メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa687-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa687-104">構文</span><span class="sxs-lookup"><span data-stu-id="aa687-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa687-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa687-105">Parameters</span></span>  
  
|<span data-ttu-id="aa687-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa687-106">Parameter</span></span>|<span data-ttu-id="aa687-107">説明</span><span class="sxs-lookup"><span data-stu-id="aa687-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="aa687-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa687-108">Return Value</span></span>  
 <span data-ttu-id="aa687-109">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="aa687-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa687-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="aa687-110">Requirements</span></span>  
 <span data-ttu-id="aa687-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="aa687-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa687-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa687-112">See also</span></span>

- [<span data-ttu-id="aa687-113">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa687-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
