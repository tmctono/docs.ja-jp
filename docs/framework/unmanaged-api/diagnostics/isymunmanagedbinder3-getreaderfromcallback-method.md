---
title: ISymUnmanagedBinder3::GetReaderFromCallback メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed0097e072b34dd43876ddf23abbc1f513670ff
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776822"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="8d410-102">ISymUnmanagedBinder3::GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="8d410-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="8d410-103">実装またはコールバックを使用していずれかを指定できます、`IID_IDiaReadExeAtRVACallback`または`IID_IDiaReadExeAtOffsetCallback`をメモリからデバッグ ディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8d410-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d410-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d410-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d410-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d410-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="8d410-106">[in]メタデータ インポート インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d410-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="8d410-107">[in]ファイル名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d410-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="8d410-108">[in]検索パスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d410-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="8d410-109">[in]値、 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)シンボル リーダーの検索を行うときに使用されるポリシーを指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="8d410-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="8d410-110">[in]コールバック関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d410-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8d410-111">[out]設定されているポインターに返された[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8d410-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d410-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="8d410-112">Return Value</span></span>  
 <span data-ttu-id="8d410-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="8d410-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d410-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d410-114">Requirements</span></span>  
 <span data-ttu-id="8d410-115">**ヘッダー:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="8d410-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d410-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d410-116">See also</span></span>

- [<span data-ttu-id="8d410-117">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d410-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
