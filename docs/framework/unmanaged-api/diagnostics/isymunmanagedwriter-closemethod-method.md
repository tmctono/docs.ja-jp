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
ms.openlocfilehash: a6a6aa937078ed0627688a4eed3d9142a2e6e0ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428107"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="d2429-102">ISymUnmanagedWriter::CloseMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d2429-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="d2429-103">現在のメソッドを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d2429-103">Closes the current method.</span></span> <span data-ttu-id="d2429-104">メソッドを閉じると、それ以上シンボルを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2429-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2429-105">構文</span><span class="sxs-lookup"><span data-stu-id="d2429-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d2429-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="d2429-106">Return Value</span></span>  
 <span data-ttu-id="d2429-107">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2429-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2429-108">要件</span><span class="sxs-lookup"><span data-stu-id="d2429-108">Requirements</span></span>  
 <span data-ttu-id="d2429-109">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d2429-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2429-110">参照</span><span class="sxs-lookup"><span data-stu-id="d2429-110">See also</span></span>

- [<span data-ttu-id="d2429-111">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2429-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d2429-112">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d2429-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
