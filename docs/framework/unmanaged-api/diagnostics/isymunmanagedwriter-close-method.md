---
title: ISymUnmanagedWriter::Close メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 0a7ecd475a8031fedb2c8474593b45045fcc6fb9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610133"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="3e793-102">ISymUnmanagedWriter::Close メソッド</span><span class="sxs-lookup"><span data-stu-id="3e793-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="3e793-103">シンボルをシンボルストアにコミットした後、シンボルライターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3e793-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e793-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e793-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3e793-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="3e793-105">Return Value</span></span>  
 <span data-ttu-id="3e793-106">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e793-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e793-107">解説</span><span class="sxs-lookup"><span data-stu-id="3e793-107">Remarks</span></span>  
 <span data-ttu-id="3e793-108">この呼び出しの後、シンボルライターは、さらに更新するために無効になります。</span><span class="sxs-lookup"><span data-stu-id="3e793-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="3e793-109">シンボルをコミットせずにシンボルライターを閉じるには、代わりに[ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e793-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e793-110">要件</span><span class="sxs-lookup"><span data-stu-id="3e793-110">Requirements</span></span>  
 <span data-ttu-id="3e793-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3e793-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e793-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e793-112">See also</span></span>

- [<span data-ttu-id="3e793-113">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e793-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
