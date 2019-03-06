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
ms.openlocfilehash: ea0cba1f1b9154ccb14d75f7c377a8153c24f2b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499486"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="2262c-102">ISymUnmanagedReader::GetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="2262c-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="2262c-103">存在する場合は、モジュールのユーザー エントリ ポイントとして指定されたメソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="2262c-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="2262c-104">たとえば、このメソッドでは、メイン メソッドの前に、コンパイラによって生成されたスタブではなく、ユーザーのメイン メソッドに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2262c-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2262c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2262c-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2262c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2262c-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="2262c-107">[out]エントリ ポイントを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2262c-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2262c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2262c-108">Return Value</span></span>  
 <span data-ttu-id="2262c-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="2262c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2262c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2262c-110">Requirements</span></span>  
 <span data-ttu-id="2262c-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2262c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2262c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2262c-112">See also</span></span>
- [<span data-ttu-id="2262c-113">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2262c-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
