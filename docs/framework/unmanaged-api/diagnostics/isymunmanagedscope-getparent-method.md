---
title: ISymUnmanagedScope::GetParent メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
ms.openlocfilehash: 95ae081d61200e4fd020609a4d23783f265d2cc6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615359"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="1df5d-102">ISymUnmanagedScope::GetParent メソッド</span><span class="sxs-lookup"><span data-stu-id="1df5d-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="1df5d-103">このスコープの親スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="1df5d-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df5d-104">構文</span><span class="sxs-lookup"><span data-stu-id="1df5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1df5d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1df5d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1df5d-106">入出力返された[ISymUnmanagedScope](isymunmanagedscope-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1df5d-106">[out] A pointer to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1df5d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="1df5d-107">Return Value</span></span>  
 <span data-ttu-id="1df5d-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1df5d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df5d-109">要件</span><span class="sxs-lookup"><span data-stu-id="1df5d-109">Requirements</span></span>  
 <span data-ttu-id="1df5d-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="1df5d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df5d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1df5d-111">See also</span></span>

- [<span data-ttu-id="1df5d-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1df5d-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="1df5d-113">GetChildren メソッド</span><span class="sxs-lookup"><span data-stu-id="1df5d-113">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)
