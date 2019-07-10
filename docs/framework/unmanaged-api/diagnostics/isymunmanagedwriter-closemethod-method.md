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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778191"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="9e83d-102">ISymUnmanagedWriter::CloseMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="9e83d-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="9e83d-103">現在のメソッドを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9e83d-103">Closes the current method.</span></span> <span data-ttu-id="9e83d-104">メソッドを終了すると、その中シンボルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="9e83d-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e83d-105">構文</span><span class="sxs-lookup"><span data-stu-id="9e83d-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9e83d-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="9e83d-106">Return Value</span></span>  
 <span data-ttu-id="9e83d-107">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9e83d-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e83d-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e83d-108">Requirements</span></span>  
 <span data-ttu-id="9e83d-109">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e83d-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e83d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e83d-110">See also</span></span>

- [<span data-ttu-id="9e83d-111">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e83d-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="9e83d-112">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="9e83d-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
