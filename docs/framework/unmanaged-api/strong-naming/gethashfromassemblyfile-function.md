---
title: GetHashFromAssemblyFile 関数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 866b34acae333f043d8e13f4d0ebd55f32046334
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140731"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="e7482-102">GetHashFromAssemblyFile 関数</span><span class="sxs-lookup"><span data-stu-id="e7482-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="e7482-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="e7482-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="e7482-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="e7482-104">This function has been deprecated.</span></span> <span data-ttu-id="e7482-105">代わりに[ICLRStrongName:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e7482-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7482-106">構文</span><span class="sxs-lookup"><span data-stu-id="e7482-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7482-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7482-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="e7482-108">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="e7482-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e7482-109">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="e7482-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="e7482-110">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7482-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e7482-111">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="e7482-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e7482-112">から要求された `pbHash`の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="e7482-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e7482-113">入出力`pbHash`の返されたサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="e7482-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7482-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="e7482-114">Requirements</span></span>  
 <span data-ttu-id="e7482-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7482-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7482-116">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="e7482-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e7482-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e7482-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7482-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7482-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7482-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7482-119">See also</span></span>

- [<span data-ttu-id="e7482-120">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="e7482-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="e7482-121">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="e7482-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="e7482-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7482-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
