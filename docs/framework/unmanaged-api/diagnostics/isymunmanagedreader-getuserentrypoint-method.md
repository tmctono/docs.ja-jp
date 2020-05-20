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
ms.openlocfilehash: d465f830fa73016c3cf3f7df3a4a4d0c42bc0980
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615502"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="f9116-102">ISymUnmanagedReader::GetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="f9116-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="f9116-103">モジュールのユーザーエントリポイントとして指定されたメソッド (存在する場合) を返します。</span><span class="sxs-lookup"><span data-stu-id="f9116-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="f9116-104">たとえば、このメソッドは、main メソッドの前にコンパイラで生成されたスタブではなく、ユーザーのメインメソッドである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9116-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9116-105">構文</span><span class="sxs-lookup"><span data-stu-id="f9116-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9116-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9116-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="f9116-107">入出力エントリポイントを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f9116-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9116-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f9116-108">Return Value</span></span>  
 <span data-ttu-id="f9116-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9116-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9116-110">要件</span><span class="sxs-lookup"><span data-stu-id="f9116-110">Requirements</span></span>  
 <span data-ttu-id="f9116-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="f9116-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9116-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9116-112">See also</span></span>

- [<span data-ttu-id="f9116-113">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f9116-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
