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
ms.openlocfilehash: 11dc050e2fe16a64db4ac95bb1386e2d90535e81
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895025"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="a9fea-102">ISymUnmanagedWriter::SetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="a9fea-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="a9fea-103">このモジュールのエントリポイントであるユーザー定義メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9fea-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="a9fea-104">たとえば、このエントリポイントは、main の前にコンパイラで生成されたスタブではなく、ユーザーのメインメソッドである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9fea-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fea-105">構文</span><span class="sxs-lookup"><span data-stu-id="a9fea-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9fea-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9fea-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="a9fea-107">からユーザーエントリポイントであるメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="a9fea-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9fea-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a9fea-108">Return Value</span></span>  
 <span data-ttu-id="a9fea-109">メソッドが成功した場合は S_OK を返します。それ以外の場合は E_FAIL またはその他のエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="a9fea-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fea-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a9fea-110">Requirements</span></span>  
 <span data-ttu-id="a9fea-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a9fea-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fea-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9fea-112">See also</span></span>

- [<span data-ttu-id="a9fea-113">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9fea-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
