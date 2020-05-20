---
title: ISymUnmanagedWriter::Abort メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610159"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="e8a72-102">ISymUnmanagedWriter::Abort メソッド</span><span class="sxs-lookup"><span data-stu-id="e8a72-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="e8a72-103">シンボルストアにシンボルをコミットせずにシンボルライターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8a72-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="e8a72-104">この呼び出しの後、シンボルライターは、さらに更新するために無効になります。</span><span class="sxs-lookup"><span data-stu-id="e8a72-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="e8a72-105">シンボルをコミットし、シンボルライターを閉じるには、代わりに[ISymUnmanagedWriter:: close](isymunmanagedwriter-close-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8a72-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a72-106">構文</span><span class="sxs-lookup"><span data-stu-id="e8a72-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e8a72-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e8a72-107">Return Value</span></span>  
 <span data-ttu-id="e8a72-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8a72-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a72-109">要件</span><span class="sxs-lookup"><span data-stu-id="e8a72-109">Requirements</span></span>  
 <span data-ttu-id="e8a72-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="e8a72-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a72-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8a72-111">See also</span></span>

- [<span data-ttu-id="e8a72-112">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8a72-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
