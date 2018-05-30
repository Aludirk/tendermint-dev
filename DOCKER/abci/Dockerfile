################################################################################
# MIT License
#
# Copyright (c) 2018 Aludirk Wong <aludirkwong@gmail.com>
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.
################################################################################

FROM golang:1.10.2-alpine3.7

RUN apk update && apk upgrade && apk add --no-cache build-base git

RUN go get "github.com/tendermint/abci/types" && \
	go get "github.com/tendermint/abci/server" && \
	go get "github.com/tendermint/tmlibs/common" && \
	go get -d "github.com/tendermint/iavl" && \
	go get "github.com/tendermint/go-amino" && \
	go get "github.com/tendermint/tmlibs/db" && \
	go get "github.com/ethereum/go-ethereum/common" && \
	go get "github.com/ethereum/go-ethereum/crypto"

WORKDIR /go/src/github.com/tendermint/iavl
RUN git checkout --track -b develop origin/develop

EXPOSE 46658

VOLUME /abci
WORKDIR /abci

ENTRYPOINT ["go"]
