---
title: ISymUnmanagedWriter::SetUserEntryPoint メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bd3d411ad6fe7f65d1eeb25754794704752009e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488358"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="6772b-102">ISymUnmanagedWriter::SetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="6772b-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="6772b-103">このモジュールのエントリ ポイントは、ユーザー定義のメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="6772b-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="6772b-104">たとえば、このエントリ ポイントでは、メインの前に、コンパイラによって生成されたスタブではなく、ユーザーのメイン メソッド可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6772b-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6772b-105">構文</span><span class="sxs-lookup"><span data-stu-id="6772b-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6772b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6772b-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="6772b-107">[in]ユーザー エントリであるメソッドのメタデータ トークンをポイントします。</span><span class="sxs-lookup"><span data-stu-id="6772b-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6772b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6772b-108">Return Value</span></span>  
 <span data-ttu-id="6772b-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6772b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6772b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6772b-110">Requirements</span></span>  
 <span data-ttu-id="6772b-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6772b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6772b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6772b-112">See also</span></span>
- [<span data-ttu-id="6772b-113">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6772b-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
