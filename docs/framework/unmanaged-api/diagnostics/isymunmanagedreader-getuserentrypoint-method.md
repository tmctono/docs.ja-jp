---
title: ISymUnmanagedReader::GetUserEntryPoint メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 995c7edf99c917b8bcdc1d51dcc0bf50868e4f35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777053"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="5a7aa-102">ISymUnmanagedReader::GetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="5a7aa-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="5a7aa-103">存在する場合は、モジュールのユーザー エントリ ポイントとして指定されたメソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="5a7aa-104">たとえば、このメソッドでは、メイン メソッドの前に、コンパイラによって生成されたスタブではなく、ユーザーのメイン メソッドに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="5a7aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a7aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a7aa-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="5a7aa-107">[out]エントリ ポイントを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a7aa-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5a7aa-108">Return Value</span></span>  
 <span data-ttu-id="5a7aa-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="5a7aa-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a7aa-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a7aa-110">Requirements</span></span>  
 <span data-ttu-id="5a7aa-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5a7aa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7aa-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a7aa-112">See also</span></span>

- [<span data-ttu-id="5a7aa-113">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a7aa-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
