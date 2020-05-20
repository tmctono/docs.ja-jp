---
title: ISymUnmanagedWriter::CloseMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: fdf24bb8533da7914128f9477987c427442383bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610120"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="6ed55-102">ISymUnmanagedWriter::CloseMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="6ed55-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="6ed55-103">現在のメソッドを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6ed55-103">Closes the current method.</span></span> <span data-ttu-id="6ed55-104">メソッドを閉じると、それ以上シンボルを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ed55-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ed55-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ed55-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6ed55-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="6ed55-106">Return Value</span></span>  
 <span data-ttu-id="6ed55-107">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ed55-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ed55-108">要件</span><span class="sxs-lookup"><span data-stu-id="6ed55-108">Requirements</span></span>  
 <span data-ttu-id="6ed55-109">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6ed55-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed55-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ed55-110">See also</span></span>

- [<span data-ttu-id="6ed55-111">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ed55-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="6ed55-112">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="6ed55-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
