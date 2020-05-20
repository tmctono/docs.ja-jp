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
ms.openlocfilehash: 4a23e9aa259f430c0d0579657952fc6aba4c307c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441657"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="65f55-102">ISymUnmanagedBinder3::GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="65f55-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="65f55-103">`IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` メモリからデバッグディレクトリ情報を取得するために、ユーザーがまたはのいずれかを使用してを実装または提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="65f55-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f55-104">構文</span><span class="sxs-lookup"><span data-stu-id="65f55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65f55-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65f55-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="65f55-106">からメタデータインポートインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="65f55-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="65f55-107">からファイル名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="65f55-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="65f55-108">から検索パスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="65f55-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="65f55-109">からシンボルリーダーの検索を実行するときに使用するポリシーを指定する[Corsymsearchpolicyattributes](corsymsearchpolicyattributes-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="65f55-109">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="65f55-110">からコールバック関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="65f55-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="65f55-111">入出力返された[ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="65f55-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65f55-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="65f55-112">Return Value</span></span>  
 <span data-ttu-id="65f55-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="65f55-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65f55-114">要件</span><span class="sxs-lookup"><span data-stu-id="65f55-114">Requirements</span></span>  
 <span data-ttu-id="65f55-115">**ヘッダー:** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="65f55-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f55-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="65f55-116">See also</span></span>

- [<span data-ttu-id="65f55-117">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65f55-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
