---
title: GetWin32ResBlob メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdc1ef6490f250ebe93b0482adf244adfc0ffd56
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741789"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="3e6b2-102">GetWin32ResBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="3e6b2-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="3e6b2-103">Win32 リソースの blob を取得します。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="3e6b2-104">アセンブリ オプションを設定した後、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e6b2-105">構文</span><span class="sxs-lookup"><span data-stu-id="3e6b2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e6b2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e6b2-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3e6b2-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3e6b2-108">Win32 バージョン リソースを作成するときに使用するファイル名を取得するために使用するファイル トークン</span><span class="sxs-lookup"><span data-stu-id="3e6b2-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="3e6b2-109">ファイルは、DLL false EXE の場合は TRUE。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="3e6b2-110">リソースの blob に挿入するオプションのアイコン。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="3e6b2-111">リソースの blob を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="3e6b2-112">Blob のサイズを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e6b2-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="3e6b2-113">Return Value</span></span>  
 <span data-ttu-id="3e6b2-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e6b2-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e6b2-115">Requirements</span></span>  
 <span data-ttu-id="3e6b2-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e6b2-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6b2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e6b2-117">See also</span></span>

- [<span data-ttu-id="3e6b2-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e6b2-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3e6b2-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e6b2-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3e6b2-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="3e6b2-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
