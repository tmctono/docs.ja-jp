---
title: ISymUnmanagedWriter::UsingNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b102f49a642d2bcd62e7f75a8dd0b9ab782ad674
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491348"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="67a4a-102">ISymUnmanagedWriter::UsingNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="67a4a-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="67a4a-103">指定した名前空間の完全修飾名が現在開いている構文のスコープ内で使用されているを指定します。</span><span class="sxs-lookup"><span data-stu-id="67a4a-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="67a4a-104">名前空間は、現在開いているスコープから継承するすべてのスコープ内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="67a4a-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="67a4a-105">現在のスコープを閉じると、名前空間の使用も停止されます。</span><span class="sxs-lookup"><span data-stu-id="67a4a-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a4a-106">構文</span><span class="sxs-lookup"><span data-stu-id="67a4a-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67a4a-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67a4a-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="67a4a-108">[in]名前空間の完全修飾名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="67a4a-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67a4a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="67a4a-109">Return Value</span></span>  
 <span data-ttu-id="67a4a-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="67a4a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67a4a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="67a4a-111">Requirements</span></span>  
 <span data-ttu-id="67a4a-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67a4a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a4a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="67a4a-113">See also</span></span>
- [<span data-ttu-id="67a4a-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67a4a-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
