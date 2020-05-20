---
title: ISymUnmanagedScope::GetStartOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 071ad6c24804eecb0f2260d54c854f22ff997bc1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611017"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="3944e-102">ISymUnmanagedScope::GetStartOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="3944e-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="3944e-103">このスコープの開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="3944e-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3944e-104">構文</span><span class="sxs-lookup"><span data-stu-id="3944e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3944e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3944e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3944e-106">入出力`ULONG32`開始オフセットを格納しているへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3944e-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3944e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3944e-107">Return Value</span></span>  
 <span data-ttu-id="3944e-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3944e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3944e-109">要件</span><span class="sxs-lookup"><span data-stu-id="3944e-109">Requirements</span></span>  
 <span data-ttu-id="3944e-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3944e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3944e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3944e-111">See also</span></span>

- [<span data-ttu-id="3944e-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3944e-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="3944e-113">GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="3944e-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
