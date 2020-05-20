---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441722"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="bf371-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="bf371-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="bf371-103">非同期操作を開始する開始メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="bf371-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf371-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf371-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf371-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf371-105">Parameters</span></span>  
  
|<span data-ttu-id="bf371-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf371-106">Parameter</span></span>|<span data-ttu-id="bf371-107">説明</span><span class="sxs-lookup"><span data-stu-id="bf371-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="bf371-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="bf371-108">Return Value</span></span>  
 <span data-ttu-id="bf371-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="bf371-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf371-110">要件</span><span class="sxs-lookup"><span data-stu-id="bf371-110">Requirements</span></span>  
 <span data-ttu-id="bf371-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="bf371-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf371-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf371-112">See also</span></span>

- [<span data-ttu-id="bf371-113">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf371-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
